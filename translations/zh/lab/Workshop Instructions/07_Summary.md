# 总结
做得好！你完成了本次研讨会，并成功为 Contoso Outdoor Company 设计了一款电商网站，充分利用了生成式 AI 的强大功能。

## 清理资源

完成教程后，您可能需要删除创建的所有资源。您可以单独删除资源，也可以删除整个资源组。

1. 浏览到 [Azure Portal](https://portal.azure.com)。
2. 从主页导航到 **资源组**，然后选择我们创建的资源组：**interact-with-llms**。

![](../../../../lab/Workshop Instructions/Images/azure-portal-resource-group.PNG)

3. 在资源组顶部导航面板中，选择 **删除资源组**。

![](../../../../lab/Workshop Instructions/Images/delete-resource-group-navigation.PNG)

4. 系统会提示您输入资源组名称以确认删除。输入名称 **interact-with-llms**，然后点击 **删除** 以删除您的资源组。

![删除资源组](../../../../lab/Workshop Instructions/Images/delete-resource-group-name.PNG)

5. 您将收到资源组已被删除的通知。

![](../../../../lab/Workshop Instructions/Images/delete-resource-group-notification-popup.PNG)

## 一些需要记住的关键点
- 生成式 AI 模型可以生成类似人类的文本、图像和代码。
- 生成式 AI 模型是无状态的：它们不会学习，并受到其冻结在某一固定时间点的训练数据的限制。
- Azure OpenAI Service 是一种托管服务，提供访问最先进的自然语言生成式 AI 模型的能力，包括来自 OpenAI 的 GPT-4、GPT-4 turbo 和 GPT-4o，同时具备 Azure 的安全性和企业级保障。
- Azure AI Foundry 是 Azure 的统一 AI 平台，代表了 Azure AI 门户和统一 SDK 体验，此外还包括预构建的应用模板以及对第三方 ISV 工具和服务的访问。
- 提示工程（Prompt engineering）是一种“引导”生成式 AI 模型的技术，可以用来影响模型输出的风格、提供事实信息以及约束意外行为。
- Azure AI Agents 是一项新功能，使开发人员更容易创建具有复杂协同工作体验的应用程序，这些应用程序可以筛选数据、建议解决方案并通过工具集成自动化任务。

## 其他资源
以下是一些资源，帮助您进一步了解 Azure OpenAI Service 和 Azure AI Foundry：

- Microsoft Learn 模块: [Azure OpenAI Service 入门](https://learn.microsoft.com/en-us/training/modules/explore-azure-openai/?WT.mc_id=aiml-132569-cacaste)
- [Azure OpenAI Service 文档](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/?WT.mc_id=aiml-132569-cacaste)
- [Azure OpenAI Service 定价](https://azure.microsoft.com/en-us/products/cognitive-services/openai-service/#pricing/?WT.mc_id=aiml-132569-cacaste)
- [Azure OpenAI Service 透明度说明](https://learn.microsoft.com/en-us/legal/cognitive-services/openai/transparency-note/?WT.mc_id=aiml-132569-cacaste) 提供了关于 Azure OpenAI 模型能力、使用案例和限制的详细信息。
- [Azure AI Foundry 入门及实现 RAG 模式](https://learn.microsoft.com/training/paths/create-custom-copilots-ai-studio//?WT.mc_id=aiml-132569-cacaste)
- [Azure AI Agents 入门](https://learn.microsoft.com/en-us/azure/ai-services/agents/overview)

**免责声明**:  
本文档通过基于机器的人工智能翻译服务翻译而成。虽然我们努力确保翻译的准确性，但请注意，自动翻译可能包含错误或不准确之处。应以原始语言的文档为权威来源。对于关键信息，建议使用专业人工翻译。因使用此翻译而导致的任何误解或错误解释，我们概不负责。