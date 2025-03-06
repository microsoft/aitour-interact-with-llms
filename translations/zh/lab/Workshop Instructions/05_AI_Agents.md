# 第四部分 - Azure AI Agents

欢迎来到本次研讨会的第四部分！

到目前为止，我们已经通过多种方式与大型语言模型进行了交互。然而，这些交互是孤立的，并且针对非常具体的目的。**Azure AI Agents** 代表了我们交互的下一步，因为它们帮助我们将之前的交互整合到一个解决方案中。

> [!TIP]  
> **什么是 Azure AI Agent？**  
> 这是一个完全托管的服务，旨在帮助开发者安全地构建、部署和扩展高质量、可扩展的 AI Agents，而无需管理底层的计算和存储资源。它集成了状态管理、上下文关联、聊天线程和代码执行等功能，从而更容易访问第三方扩展。

之前，即使是经验丰富的开发者，构建自定义 AI Agents 也需要耗费大量精力。虽然聊天补全 API 轻量且功能强大，但它本质上是无状态的，这意味着开发者需要手动管理会话状态和聊天线程、工具集成、检索文档和索引，以及执行代码。

在 Azure AI Foundry 中，AI Agent 作为一个“智能”微服务，可以用来回答问题（RAG）、执行操作或完全自动化工作流。它通过结合生成式 AI 模型的强大功能和能够访问和交互现实数据源的工具来实现这一点。

如果需要，Agents 还可以并行访问多个工具。这些工具包括：
- **Function Calling**
- **代码解释器**
- **文件搜索**
- **基于 Bing 的搜索**
- **Azure Functions** 等等。

在本节中，我们将重点讲解代码解释器。

## 理解 Agents 的组成部分

开始使用 Azure AI Agents 之前，理解和掌握其功能涉及的不同组成部分非常重要。

正如我们现在所知，**Agent** 只是一个“智能”微服务，可以通过 RAG 回答问题、执行操作或自动化工作流。

创建 Agent 后的下一步是创建一个 **Thread**。**Thread** 是 Agent 与用户之间的会话。线程存储消息，并自动处理截断以将内容适配到模型的上下文中。

**Messages** 是由 Agent 或用户创建的，可以包括文本、图片和其他文件。这些消息以列表的形式存储在线程中。

最后，我们可以 **运行（Run）** Agent。这意味着激活 Agent，根据线程的内容开始运行。Agent 使用其配置和 *线程的消息* 通过调用模型和工具来执行任务。作为运行的一部分，Agent *将消息附加到线程中*。

## 创建 Agent

1. 在左侧导航栏的 _Build and customize_ 下，选择 **Agents**。在新打开的页面中，点击下拉箭头选择你的 Azure OpenAI Service 资源，然后点击 **Let's go** 按钮。

![选择 Azure OpenAI Service 资源的截图](../../../../lab/Workshop Instructions/Images/agents-aoai-select.jpeg)

2. 系统会为你自动创建一个新的 Agent。在 **Deployments** 部分，确保选择 **gpt-4o-mini** 模型。

    > [!TIP]  
    > **确保选择正确的部署**。应显示为 **gpt-4o-mini** 及其版本。

3. 接下来，为你的 Agent 命名。在 Agent Name 文本框中输入以下内容：

    ```Contoso Outdoor Sales Agent```

4. 接下来，我们可以为 Agent 提供 **指令**。类似于之前部分提到的 *系统消息*，它为 Agent 提供需要遵循的目标。导航到 **Prompt** 选项卡，将以下指令复制到 Instructions 文本框中。

    ``` 
    You are a sales Agent for Contoso Outdoor. You are polite, professional, helpful and friendly.

    You get all the sales data from the uploaded .csv files. There is sales revenue data that is broken down by region, product category, product type and separated by year and month.

    Examples of regions include Africa, Asia, Europe and America. Categories include climbing gear, camping equipment, apparel and others. Product categories include jackets, hammocks, wet suits, shoes and more. 

    If a question is not related to sales or you cannot answer the question, you **must** respond: "Please contact IT for more assistance". If the user asks for help or says 'help', provide a list of sample questions that you can answer.
    ```

    ![Agents Playground](../../../../lab/Workshop Instructions/Images/agents-playground-update-details.jpeg)

    > [!NOTE]  
    > 你能在此提示中识别出之前部分提到的多少种提示工程技术？提示：查看本研讨会的第二部分。

5. 导航到 **Actions** 选项卡，并点击 **add**。

    ![Agent 添加新文件](../../../../lab/Workshop Instructions/Images/agents-actions.jpeg)

6. 将打开一个新选项卡，选择 **代码解释器（Code Interpreter）**。

7. 在接下来的窗口中，点击 **选择本地文件（select local files）**，然后选择 `Contoso_Sales_Revenue.csv` file on your Desktop.
    ![Agents code interpreter](../../../../lab/Workshop Instructions/Images/aifoundry-codeinterpreter-upload-file.jpeg)

    >[!NOTE]
    > If you cannot find the file on your desktop, you can download it from [here](../../../../lab/Workshop Instructions/assets/Contoso_Sales_Revenue.csv).

7. Click on the **upload and add** button. You should now see the file under the *Code Interpreter* tool.

The Agent is now ready for us to interact with it.

## Interacting with our Agent

1. On the top right of our Agents window, select **Try in playground**

![](../../../../lab/Workshop Instructions/Images/agents-try-in-playground.jpeg)

2.  Let's begin by typing `help`。在聊天框中，你会注意到这开启了一个新线程。  
   你会看到一些示例问题可以测试。尝试其中一个问题，看看 Agent 的回复！

8. 接下来，让我们尝试一个具体的查询。输入以下内容：

    ```What are the total sales for Europe broken down by category? ```

    你会注意到 Agent 使用代码解释器为你提供了答案。

9. 现在，让我们尝试处理这些数据。输入以下提示：

    ```Put this data in a graph. ```

    通过代码解释器，Agent 能够将结构化数据转换为图表！

10. 如果你想查看另一种类型的图表，尝试以下提示并请求数据以图表形式展示：

    ```What is the trending product category? Give the output as a graph. ```

    Agent 将通过分析销售收入数据随时间的变化，为你提供一个显示趋势产品的图表。

恭喜！你已经完成了研讨会的最后部分，并学习了 Azure OpenAI Assistants 是什么、它们如何工作以及如何使用 Azure AI Studio 创建它们。

前往研讨会的最后部分：[总结](./07_Summary.md)

**免责声明**：  
本文件使用基于机器的人工智能翻译服务进行翻译。尽管我们努力确保准确性，但请注意，自动翻译可能包含错误或不准确之处。应以原始语言的文件作为权威来源。对于关键信息，建议使用专业的人类翻译服务。我们对于因使用本翻译而导致的任何误解或误读不承担责任。