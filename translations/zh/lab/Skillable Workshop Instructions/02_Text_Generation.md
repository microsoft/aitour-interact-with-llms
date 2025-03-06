# 第 1 部分 - 文本生成

欢迎来到本次研讨会的第 1 部分，我们将与 gpt-4o-mini 模型互动以生成文本。

> [!TIP]
> 什么是提示工程？
> 提示工程是自然语言处理（NLP）中的一个概念，它通过在输入中**嵌入任务描述**来**提示模型**输出**所需的结果**。

## 基础提示

让我们从一些基础提示开始，并通过聊天界面观察响应。要使用聊天界面，请按照以下步骤操作：

![显示聊天界面的图片](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-basicprompting.jpeg)

1. 导航到左侧导航栏的“Playgrounds”部分，然后点击 **Try the Chat Playground**。
2. 在聊天界面中，找到标有 _"Type user query here."_ 的文本框。
3. 从以下提示示例中，点击 "T"（例如，``here is a sample prompt``），这将自动将内容插入到当前光标位置，只需单击一下。
4. 添加提示后，找到通常位于输入框旁边的纸飞机图标。点击纸飞机图标，将文本提交到模型部署。
5. 提交查询后，稍等片刻，让模型处理并响应。响应将显示在输入框下方的聊天窗口中。

以下是一些示例可以尝试，但也可以发挥创造力，使用自己的提示看看会发生什么！

### 网站文案和对话历史

```
Suggest a tagline for the website landing page of an ice cream shop called SweetScoops Delight.
```

在不清除聊天历史的情况下，现在尝试以下提示：

```
Generate website copy for the homepage of the ice cream shop.
```

注意，模型正在为 *SweetScoops Delight* 网站提供文案，即使我们没有再次指定公司名称或业务。这是因为模型在后台将**整个对话历史**作为上下文，而不仅仅是最新的提示。AI 模型无法学习，也无法记住用户离开后再次返回的交互内容，但应用程序使用提示工程来添加这种“记忆”。

> [!NOTE]
> 您可以控制上下文窗口大小，也就是模型会考虑为上下文的先前交互数量（默认是 10），可以在 **Parameters** 部分进行调整。

您可以按以下步骤控制模型参数：

![显示参数选项卡的图片](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-parameters.jpeg)

1. 在聊天界面中，导航到 **Parameters** 部分。
2. 进入参数部分后，调整设置控件。您可以更改模型会考虑为上下文的过去消息数量。设置完成后，修改将自动生效。

### 摘要和关键实体提取

我们从上一步中得到的文案已经是一个不错的起点，但它可能对于登陆页面来说太长了。让我们尝试获取一个简短的版本。

文本摘要是大型语言模型（LLMs）的一个广为人知的能力，它可以从较长的文本中生成简短摘要。

> [!TIP]
> 想要生成摘要，可以在提示中添加 tl;dr（表示“太长了；没读”），后面跟上您想要摘要的文本。

此外，您还可以指示您的 LLM 从文本中提取关键信息。在我们的场景中，这对于获取**SEO 优化**的关键词非常有用。尝试以下提示来总结前面的文案，然后提取有用的数据。

```
1. tl;dr
2. Extract company name, categories of products and business unique values from the long description above.
```

## 高级提示

>[!alert] 在进入下一部分之前，点击 **Clear Chat** 按钮清除消息历史。为此，请点击右上角的**扫帚图标**。会弹出一个窗口，点击 **clear button** 清除聊天记录。

![清除聊天按钮的截图](../../../../lab/Skillable Workshop Instructions/Images/text-generation-clearchat.jpg)

### 零样本学习

LLMs 在训练时接触了大量数据，它们可能能够通过非常少的提示完成某些任务。这被称为**零样本学习**。例如，让我们要求模型生成一个产品名称列表并对其分类：

```
Generate 10 unique menu items for a futuristic themed restaurant, including dish names and a short description.
```
>[!alert] 在进入下一部分之前，点击 **Clear Chat** 按钮清除消息历史。

### 少样本学习

如果零样本学习对您的示例和更复杂的任务不起作用，**少样本提示**可以通过提供示例更好地引导模型达到期望的结果。示例清晰地向模型展示我们希望它如何操作。以下是一个用于对产品进行分类的少样本学习提示示例。

```
Generate 10 unique pizza menu items with futuristic names, including the name of the pizza and a short description.

Examples:  
The Nebula Supreme: A classic supreme pizza with pepperoni, sausage, bell peppers, onions, and olives, topped with a hint of spicy marinara sauce.
Galactic Garden: A vegetarian delight featuring spinach, cherry tomatoes, mushrooms, and artichokes with a basil pesto drizzle.
Asteroid Meat Feast: Loaded with pepperoni, ham, ground beef, bacon, and Italian sausage for a hearty, protein-packed slice.
```

### 思维链提示

>[!alert] 开始之前，请点击 **Clear Chat** 以避免之前交互的任何上下文干扰。

与 LLMs 交互时，一个有用的技巧是想象您正在与一个未经训练的实习生交谈。因此，您提供的任务细节越多，获得的结果就越好。特别地，一个有用的策略是将任务分解为较小的部分，并为每个部分提供提示。让我们在网站文案生成任务中尝试这一点。

```
Develop a new pizza for our restaurant.

Instructions:
- Start by deciding on a theme for the new pizza.
- Determine the overall flavor profile. Should it be spicy, sweet, savory, or a mix?
- Pick the base ingredients. This includes the type of sauce and cheese
- Think about unique toppings that fit the theme and flavor profile.
- Finally, come up with a creative, memorable name that fits both the futuristic theme of the restaurant and the flavor experience you’ve crafted.
```

另一种选择是使用一种称为**思维链**的技术，其中 LLM 负责将任务分解为更小的步骤。LLM 使用其对世界的知识及其推理能力生成一系列思路，最终得出任务的解决方案。再次清除聊天记录，然后输入以下用户提示，看看“思维链提示”的实际效果：

```
Develop a new pizza for our restaurant.

Take a step-by-step approach in your response: Start by thinking about the theme, considering how it fits into the restaurant's overall futuristic concept. Then, define the flavor profile, keeping in mind our audience's preferences and the overall taste experience you want to create. Next, choose the base ingredients, including the sauce type and cheese blend, and think about unique toppings that make this pizza stand out. Finally, decide on a name that aligns with the theme and enhances the pizza's appeal. Include your reasoning before sharing the final answer in the below format: ANSWER is: <pizza description>.
```

## 系统消息和新增知识

>[!alert] 在进入下一部分之前，点击 **Clear Chat** 按钮清除消息历史。

### 系统消息

> [!TIP]
> 什么是**系统消息**？系统消息用于在对话开始时向模型传达指令或提供上下文。它以不同于用户消息的格式显示，帮助模型理解其在对话中的角色。系统消息通常指导模型的行为、设定语气或指定所需的输出。通过有效利用系统消息，用户可以引导模型生成更准确和相关的响应。

![显示系统消息选项卡的图片](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-instructions.jpeg)

按以下步骤更新系统消息，为模型提供指令和上下文：

1. 在聊天界面中，导航到 **System message** 部分。
2. 进入系统消息部分后，删除现有消息。点击系统消息字段，将光标放置在其中，然后插入以下文本：

```
## Task
You are a menu designer for a futuristic-themed pizzeria restaurant named "Galactic Slice". Your goal is to generate creative menu items and descriptions. Keep your answers brief, engaging, and aligned with the restaurant's theme.

Your answer should be brief and engaging. Always use a friendly and professional tone of voice.

## Safety
Keep the descriptions family-friendly and suitable for all age groups visiting our pizzeria. Avoid any irrelevant information and controversial opinions.
```

3. 找到标有 Apply changes 的按钮，它位于系统消息框的正下方。点击此按钮保存并应用您对系统消息字段所做的更改。
4. 应用更改后，点击弹出窗口中的 **continue button** 更新系统消息。

观察我们如何为模型提供**明确的任务**、**语气要求**和**安全措施**。您的模型就像您业务中使用的任何技术工具一样，是您的品牌的一部分。如果您希望它具备与您的行为准则一致的方法和伦理，这些也应包含在您的 AI 解决方案中。在系统消息中设置语气相关内容可以帮助调整响应类型以适应您的使用场景。

系统消息中的文本由模型特别处理，其对模型响应的影响力比用户消息文本或提示中提供的其他上下文更大。此外，它会在聊天中的所有交互中保持不变，即使您清除了聊天记录。

5. 为了查看添加上下文后模型行为的变化，请在文本框中尝试以下提示：

```
Write a brief description of the restaurant, including the categories of menu items offered.
```

您会看到，模型不仅响应了请求的信息，还准确地完成了任务，例如保持餐厅主题和名称的一致性。进一步测试时，我们可以验证**安全措施**：

```
What are your thoughts on the just concluded election?
```

6. 模型将拒绝对此作答（因为它既与公司无关，又可能被视为有争议），并坚持围绕公司及其产品展开。

### 基于事实的提示

>[!alert] 在进入本部分之前，请确保点击 **Clear Chat** 清除聊天记录。

到目前为止，模型在创造性地发明业务价值主张和产品（菜单）方面表现出色。然而，在现实世界的场景中，我们希望模型生成的文本是基于事实的，并反映实际业务。为此，我们可以使用一种称为**检索增强生成（RAG）**的技术。此技术通过向模型提供一组关于业务的事实或信息，使模型能够生成更准确和相关的文本。

> [!NOTE]
> **检索增强生成（RAG）** 是一种结合语言模型与搜索系统的 AI 技术，能够提供更准确和详细的信息。在 RAG 模式中，系统通常从数据库中检索相关信息，然后使用这些信息帮助生成更有见地和上下文准确的文本响应。在本实验中，我们将通过在提示中提供一组业务事实来模拟检索过程。

让我们切换到另一个场景，为 Contoso Outdoor Company 生成基于其产品目录的文案。可以通过系统消息提供新增的产品知识。在现有系统提示的末尾插入以下信息，然后点击 **Apply changes**。

```
## Business Information
Contoso Outdoor Company is an e-commerce business that specializes in outdoor clothing and equipment. The company offers a wide range of products, including tents, backpacks, hiking clothing, and sleeping bags. The company's main value proposition is to provide high-quality outdoor gear for every level of outdoor enthusiast at affordable prices.

Products offered:
1. Tents: 
    - TrailMaster X4 Tent: Crafted from durable polyester, this tent boasts a spacious interior perfect for four occupants. It ensures your dryness under drizzly skies thanks to its water-resistant construction, and the accompanying rainfly adds an extra layer of weather protection.
    - Alpine Explorer Tent: This robust, 8-person, 3-season marvel is from the responsible hands of the AlpineGear brand. Promising an enviable setup that is as straightforward as counting sheep, your camping experience is transformed into a breezy pastime.
    - SkyView 2-Person Tent: This tent offers a spacious interior that houses two people comfortably, with room to spare. Crafted from durable waterproof materials to shield you from the elements, it is the fortress you need in the wild. 

2. Backpacks:
    - Adventurer Pro Backpack: Uniquely designed with ergonomic comfort in mind, this backpack ensures a steadfast journey no matter the mileage. It boasts a generous 40L capacity wrapped up in durable nylon fabric ensuring its long-lasting performance on even the most rugged pursuits. 
    - SummitClimber Backpack: your reliable partner for every exhilarating journey. With a generous 60-liter capacity and multiple compartments and pockets, packing is a breeze. Every feature points to comfort and convenience; the ergonomic design and adjustable hip belt ensure a pleasantly personalized fit, while padded shoulder straps protect you from the burden of carrying. 
    - TrailLite Daypack: Built for comfort and efficiency, this lightweight and durable backpack offers a spacious main compartment, multiple pockets, and organization-friendly features all in one sleek package. 

3. Hiking Clothing:
    - Summit Breeze Jacket: This lightweight jacket is your perfect companion for outdoor adventures. Sporting a trail-ready, windproof design and a water-resistant fabric, it's ready to withstand any weather. 
    - TrailBlaze Hiking Pants: Crafted from high-quality nylon fabric, these dapper troopers are lightweight and fast-drying, with a water-resistant armor that laughs off light rain. Their breathable design whisks away sweat while their articulated knees grant you the flexibility of a mountain goat.
    - RainGuard Hiking Jacket: the ultimate solution for weatherproof comfort during your outdoor undertakings! Designed with waterproof, breathable fabric, this jacket promises an outdoor experience that's as dry as it is comfortable.
```

为了查看添加上下文后模型行为的变化，请尝试以下提示：

```
Write a short description for each of the following product categories: tents, backpacks, hiking clothing.
```

## 后续步骤

恭喜您完成了实验的第一部分！您已经学习了如何使用提示工程通过语言模型生成文本。在实验的下一部分，您将学习如何使用模型生成图像素材。

点击 **Next** 进入图像部分。

**免责声明**：  
本文件使用基于机器的人工智能翻译服务进行翻译。尽管我们尽力确保准确性，但请注意，自动翻译可能包含错误或不准确之处。应以原始语言的文件为权威来源。对于关键信息，建议寻求专业人工翻译。我们对于因使用此翻译而引起的任何误解或误读不承担责任。