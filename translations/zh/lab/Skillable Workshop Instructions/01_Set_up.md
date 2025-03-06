# 开始使用

> [!TIP]  
> 什么是 **Azure AI Foundry**？Azure AI Foundry 是一个为创新者打造未来的终极平台。它提供了一整套 Azure AI 功能和工具，用于设计、定制和管理 AI 应用和代理。它与全球最受欢迎的开发者工具无缝集成，包括 GitHub、Visual Studio 和 Copilot Studio。Azure AI Foundry 让开发者和 IT 管理员能够轻松高效地实现他们的 AI 愿景。

## 登录 Windows  
第一步，使用以下凭据登录实验室虚拟机：  
- 用户名：已设置为 Admin。  
- 密码：输入 +++@lab.VirtualMachine(Win11Base23B-W11-22H2).Password+++ 并点击。  

> [!TIP]  
> 第一次使用 **Skillable**？绿色的 "T"（例如，+++Admin+++）表示可以通过单击在虚拟机的当前光标位置自动输入的值。这可以减少你的操作并降低输入错误的可能性。

## 登录 Azure AI Foundry 门户  

在本次研讨会中，我们将使用 Azure AI Foundry 门户，特别是其 Playground 功能。

1. 在桌面上，点击 **Microsoft Edge** 浏览器。导航到第二个浏览器标签页，该标签页将显示 Azure AI Foundry 门户主页，如下图所示。

![Azure AI Foundry 首页](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-homepage.jpeg)

## 浏览 Azure AI Foundry 门户  

1. 点击 **登录**，你可以在窗口右上角找到登录链接，并在系统提示输入登录凭据时输入以下信息：  
    - 邮箱：+++@lab.CloudPortalCredential(User1).Username+++  
    - 密码：+++@lab.CloudPortalCredential(User1).Password+++  

    现在我们已登录，可以开始浏览该平台。  

2. 在可用的 Hubs 列表中找到 **Workshop AI Hub**。**点击该 Hub 中的项目**以访问其设置和资源。  

![Hub 管理标签](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-hub-navigation.jpeg)

## 项目  

![项目概览标签](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-project-overview.jpeg)

### 项目概览  

在此页面中，我们可以看到 Azure AI Foundry 门户项目的概览，其中包括：  
- **项目名称和描述**：项目名称以及 Azure AI Foundry 门户项目的简短描述。  
- **项目详情**：各种属性的集合，例如项目的连接字符串、位置、资源组等。  
- **端点和密钥**：Azure AI Foundry 门户允许连接多个资源，扩展其功能。这些资源包括 Azure OpenAI、Azure AI Search 和 Azure AI Services，进一步增强了项目的能力，使我们可以访问如 LLM 部署或向量搜索等功能。在这里，我们可以找到诸如 *API 端点和密钥* 以及文档等有用信息。  
- **最近的资源和教程**：在此部分，你最近使用的资源会被突出显示，同时提供额外的学习资源和教程，帮助你快速入门。

### 导航栏  

你会注意到导航栏已更新为新标签，这些标签代表与我们项目相关的功能。  

![项目导航栏](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-project-navigation.jpeg)

我们有以下新部分：  
1. 第一个部分包括 _Playgrounds_ 用于与模型交互，_Overview_ 提供项目的总体概览，_Model Catalog_ 展示 Azure AI Foundry 内可用的模型，以及 _AI Services_，可以查看可用的 Azure AI Services 列表以及演示、用例等内容。  
1. **构建与定制**：包括扩展项目范围的有用功能，例如通过运行云计算在 _Code_ 中工作，访问 [_Prompt Flow_](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow)，以及对部署进行 _Fine Tuning_。  
1. **评估与改进**：包括为模型开发 _Evaluations_，通过 _tracing_ 调试流程，以及通过 _content filters_ 为提示输入和输出添加防护措施。  
1. **我的资产**：在这里你可以为项目添加额外的元素，包括 _数据_、_索引_、_模型和端点_ 以及 _Web 应用_，以便作为工作的一部分使用。  
1. **管理中心**：一个用于管理所有 Hub 和项目详细信息及资源的位置。

在本次实验中，我们将专注于使用 **Playgrounds**，导航到 Playgrounds 并继续下一部分。

## Playgrounds  

你会注意到我们有多个 **Playground** 选项。每个选项代表一种与 AI 模型交互和使用的不同方法，可以根据我们的具体需求进行定制。  

我们的大部分工作将在这些 Playgrounds 中进行，特别是在以下几个：  

1. **聊天 Playground**  
1. **图像 Playground**  
1. **实时音频 Playground**  
1. **代理 Playground**  

![Azure AI Foundry Playgrounds 图像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-playgrounds.jpeg)

### 聊天 Playground  

在 Playground 部分中，导航到 **聊天 Playground** 并选择 **尝试聊天 Playground**。此功能允许你以对话形式与各种 AI 模型进行交互和测试。  

![Azure AI Foundry Playground 聊天模式图像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-playground.jpeg)

1. **部署**：此部分允许我们在已部署的模型之间切换。  
1. **系统消息框**：在这里输入模型的指令，供用户交互之前使用。  
1. **添加你的数据**：Azure AI Foundry 门户支持为已部署的模型提供外部数据，从而实现更好的搜索和上下文。  
1. **参数**：此标签包含模型的详细设置，例如温度。  
1. **聊天框**：聊天框显示我们与模型的交互内容，以聊天消息的形式呈现。  
1. **提示框**：这是我们输入想要发送给模型的提示内容的地方。

### 图像 Playground  

返回到 Playgrounds，选择 **图像 Playground** 并点击 **尝试图像 Playground**。此选项允许你进行图像生成。  

![Azure AI Foundry Playground 图像模式图像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-image-playground.jpeg)

1. **部署**：在此下拉菜单中，我们可以选择用于图像生成的模型。这些模型与聊天模型一样，来自我们的部署。  
1. **提示框**：与聊天 Playground 的提示框类似，这是用户输入内容的地方。在图像生成的情况下，是描述我们想要生成的内容。  
1. **结果框**：最后，生成的图像会显示在这里。

### 实时音频 Playground  

返回到 Playgrounds，然后选择 **实时音频 Playground** 并点击 **尝试实时音频 Playground**。此功能允许你以音频对话的形式与各种 AI 模型进行交互和测试。  

![Azure AI Foundry Playground 实时音频模式图像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-real-time-audio.jpeg)

1. **部署**：此部分允许我们在已部署的模型之间切换。  
1. **服务器回合检测**：决定服务器是否使用语音活动检测 (VAD) 来识别用户何时结束讲话。  
1. **系统消息框**：在这里输入模型的指令，供用户交互之前使用。  
1. **选择语音**：gpt-4o-realtime 提供多种语音可供选择，具有独特的口音或语调能力，满足你的需求。  
1. **服务器回合检测**：附加参数，用于通过改进语音活动检测来优化模型的效率和性能。  
1. **参数**：此标签包含模型的详细设置，例如温度和最大响应。  
1. **提示按钮**：与聊天 Playground 的提示框类似，这是用户输入内容的地方。

## 代理 Playground  

在导航栏中，选择 **Agents**。此功能为你提供构建、测试和定制 AI 驱动代理的工具。  

![Azure AI Foundry Playground 代理模式图像](../../../../lab/Skillable Workshop Instructions/Images/agents-playground-pt1.jpeg)

当你 _创建第一个代理_ 时，你会看到以下 UI 组件：  
1. **代理 ID 和名称**：在这里你可以为代理命名。  
1. **部署**：在此下拉菜单中，我们可以选择用于代理的模型。这些模型与聊天模型一样，来自我们的部署。  
1. **指令框**：在这里输入模型的指令，供用户交互之前使用。

![](../../../../lab/Skillable Workshop Instructions/Images/agents-playground-pt2.jpeg)

4. **知识**：知识使代理能够访问数据源以增强回答的准确性。  
1. **动作**：通过允许代理在运行时使用各种工具来增强其能力。  
1. **模型设置**：此标签包含模型的详细设置，例如温度和 Top P。  
1. **提示框**：与聊天 Playground 的提示框类似，这是用户输入内容的地方。

## 准备开始  

以上是 Azure AI Foundry 门户的必要设置和基础知识。接下来，我们将开始与模型交互。

- 导航到 **Playgrounds**，选择 **聊天 Playground** 并点击 **尝试聊天 Playground**。  
- 在 _指令标签_ 中，点击下一步进入第 1 部分：文本生成。

点击 **下一步** 进入文本生成部分。  

**免责声明**：  
本文件使用基于机器的人工智能翻译服务进行翻译。尽管我们努力确保翻译的准确性，但请注意，自动翻译可能包含错误或不准确之处。应以原始语言的文件为权威来源。对于关键性信息，建议使用专业人工翻译。我们对因使用本翻译而引起的任何误解或误读不承担责任。