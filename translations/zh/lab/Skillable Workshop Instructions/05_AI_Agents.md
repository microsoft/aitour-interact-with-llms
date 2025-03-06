# 第四部分 - Azure AI Agents

欢迎来到本次研讨会的第四部分！

到目前为止，我们已经通过多种方式与大型语言模型进行交互。然而，这些交互是孤立的，并且与非常具体的目的相关联。**Azure AI Agents** 代表了我们交互的下一步，因为它们帮助我们将之前的交互整合到一个解决方案中。

> [!TIP]  
> **什么是 Azure AI Agent？** 是一种完全托管的服务，旨在帮助开发者安全地构建、部署和扩展高质量、可扩展的 AI Agent，而无需管理底层的计算和存储资源。它集成了状态管理、上下文关联、聊天线程和代码执行等功能，使得访问第三方扩展变得更加容易。

以前，即使是经验丰富的开发者，构建自定义 AI Agent 也需要付出很大的努力。虽然聊天补全 API 功能强大且轻量，但它本质上是无状态的，这意味着开发者需要手动管理会话状态和聊天线程、工具集成、文档检索和索引以及代码执行。

在 Azure AI Foundry 中，AI Agent 充当一个“智能”微服务，可以用来回答问题（RAG）、执行操作或完全自动化工作流。它通过结合生成式 AI 模型的强大功能与能够访问和交互真实世界数据源的工具来实现这一点。

如果需要，Agent 还可以并行访问多个工具。这些工具包括：
- **Function Calling**
- **Code Interpreter**
- **File Search**
- **基于 Bing 搜索的基础支持**
- **Azure Functions** 等等。

在本节中，我们将重点介绍 Code Interpreter。

## 了解 Agent 的组成部分

在开始使用 Azure AI Agent 之前，重要的是要理解并掌握其功能涉及的不同组成部分。

正如我们现在所了解的，**Agent** 只是一个“智能”微服务，可以通过 RAG 回答问题、自动化工作流或执行操作。

创建 Agent 后的下一步是创建一个 **Thread**。**Thread** 是 Agent 和用户之间的会话。线程存储消息，并自动处理内容截断以适配模型的上下文。

**消息** 由 Agent 或用户创建，包括文本、图像和其他文件。这些消息以列表形式存储在线程中。

最后，我们可以 **运行** Agent。这意味着激活 Agent 以基于线程的内容开始运行。Agent 使用其配置和 *线程的消息* 通过调用模型和工具来执行任务。作为运行的一部分，Agent 会将 *消息附加到线程*。

## 创建 Agent

1. 在左侧导航栏的 _Build and customize_ 下，选择 **Agents**。在刚刚打开的页面中，点击下拉箭头以选择您的 Azure OpenAI Service 资源，然后点击 **Let's go** 按钮。

![选择 Azure OpenAI Service 资源的截图](../../../../lab/Skillable Workshop Instructions/Images/agents-aoai-select.jpeg)

2. 一个新的 Agent 会自动为您创建。在 **Deployments** 部分，确保选择 **gpt-4o-mini** 模型。

   > [!TIP]  
   > **确保选择正确的部署。** 它应该显示为 **gpt-4o-mini** 及其版本。

3. 接下来，为 Agent 命名。在 Agent Name 文本框中输入以下内容：

   ```Contoso Outdoor Sales Agent```

4. 然后，我们可以为 Agent 提供一条 **指令**。类似于我们在前面章节中看到的 *系统消息*，它为 Agent 提供需要遵循的目标。导航到 **Prompt** 标签页，将以下指令复制到 Instructions 文本框中。

   ``` 
    You are a sales Agent for Contoso Outdoor. You are polite, professional, helpful and friendly.

    You get all the sales data from the uploaded .csv files. There is sales revenue data that is broken down by region, product category, product type and separated by year and month.

    Examples of regions include Africa, Asia, Europe and America. Categories include climbing gear, camping equipment, apparel and others. Product categories include jackets, hammocks, wet suits, shoes and more. 

    If a question is not related to sales or you cannot answer the question, you **must** respond: "Please contact IT for more assistance". If the user asks for help or says 'help', provide a list of sample questions that you can answer.
    ```

   ![Agents Playground](../../../../lab/Skillable Workshop Instructions/Images/agents-playground-update-details.jpeg)

   > [!NOTE]  
   > 您能在这个提示中识别出多少前面章节提到的提示工程技术？提示：查看研讨会的第二部分。

5. 导航到 **Actions** 标签页，并点击 **add**。

   ![Agent 添加新文件](../../../../lab/Skillable Workshop Instructions/Images/agents-actions.jpeg)

6. 新选项卡中选择 **Code interpreter**。

7. 在下一个窗口中，点击 **select local files** 并选择 `Contoso_Sales_Revenue.csv` file on your Desktop.
    ![Agents code interpreter](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-codeinterpreter-upload-file.jpeg)

    >[!NOTE]
    > If you cannot find the file on your desktop, you can download it from [here](../../../../lab/Skillable Workshop Instructions/assets/Contoso_Sales_Revenue.csv).

7. Click on the **upload and add** button. You should now see the file under the *Code Interpreter* tool.

The Agent is now ready for us to interact with it.

## Interacting with our Agent

1. On the top right of our Agents window, select **Try in playground**

![](../../../../lab/Skillable Workshop Instructions/Images/agents-try-in-playground.jpeg)

2.  Let's begin by typing `help` 文件。您会注意到这会开启一个新线程。  
   您会看到一些可以测试的示例问题。尝试其中一个问题，看看 Agent 的回复！

8. 接下来，让我们尝试一个具体查询。在聊天框中输入以下内容：

   ```What are the total sales for Europe broken down by category? ```

   您会注意到 Agent 使用 Code Interpreter 为您提供答案。

9. 现在，让我们尝试处理这些数据。在聊天框中输入以下提示：

   ```Put this data in a graph. ```

   通过 Code Interpreter，Agent 能够将结构化数据转换为图表！

10. 如果您想查看另一种类型的图表，可以尝试以下提示，并请求数据以图表形式展示：

    ```What is the trending product category? Give the output as a graph. ```

    Agent 应该通过分析销售收入数据随时间的变化，为您提供一个展示热门产品趋势的图表。

恭喜！您现在已经完成了研讨会的最后一部分，学习了什么是 Azure OpenAI Agent，它们如何工作，以及如何使用 Azure AI Foundry 门户创建一个 Agent。

点击 **Next** 进入研讨会的总结部分。

**免责声明**：  
本文件通过机器翻译服务翻译而成。尽管我们努力确保翻译的准确性，但请注意，自动翻译可能包含错误或不准确之处。应以原始语言的文件作为权威来源。对于关键信息，建议寻求专业人工翻译。因使用本翻译而导致的任何误解或误读，我们概不负责。