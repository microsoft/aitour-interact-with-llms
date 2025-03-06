# 第2部分：图像生成

欢迎来到本次工作坊的第2部分，我们将与文本生成图像模型 DALL-E 3 进行互动。

> [!TIP]
> 什么是 DALL-E 3？DALL-E 3 是一种基于神经网络的模型，可以根据**自然语言输入**生成图像数据。简单来说，你可以向 DALL-E 3 提供一个**描述**，它就能生成相应的图像。

## 创建你的第一张图像

要创建你的第一张图像，请按照以下步骤操作：

![展示图像生成的图片](../../../../lab/Workshop Instructions/Images/aifoundry-image-generation.jpeg)

1. 导航到左侧导航栏的 **playgrounds**，然后选择 **Try the Image Playground**。
2. 在 Images playground 中，找到并点击标有 **Deployments** 的下拉菜单。从下拉列表中选择 **dall-e-3**。
3. 在 Images playground 中，找到标有 _"Describe the image you want to create."_ 的文本框。从以下的提示示例中，点击 "T"（例如，``here is a sample prompt``），它会自动将内容插入到当前光标位置。
4. 输入你的描述后，会出现一个 **Generate** 按钮。点击按钮，将你的图像描述提交到模型部署。
5. 提交查询后，稍等片刻，让模型进行处理并响应。响应结果将显示在输入框下方的窗口中。

让我们通过在描述框中输入一个基础提示并点击生成来开始生成图像：

```a watercolor painting of Chicago skyline```

这将生成类似以下的图像：

![水彩风格的城市天际线](../../../../lab/Workshop Instructions/Images/DALL·E%202024-11-14%2009.27.57%20-%20A%20watercolor%20painting%20of%20the%20Chicago%20skyline,%20showcasing%20iconic%20skyscrapers%20such%20as%20the%20Willis%20Tower%20and%20John%20Hancock%20Center.%20The%20city%20is%20bathed%20in%20so.webp)

DALL-E 3 生成的图像是原创的；它们并非从某个图片目录中检索而来。换句话说，DALL-E 3 不是一个搜索系统，而是一个基于其训练数据生成新图像的人工智能 (AI) 模型。

### 具体化描述

详细描述可以让模型的响应更加准确。与文本生成类似，图像生成模型在接收到具体的描述时会表现得更好。

1. 例如，输入以下提示：

    ```A logo for an adventure brand```

2. 然后选择 **Generate**，查看生成的图像。

    ![冒险品牌的标志](../../../../lab/Workshop Instructions/Images/Generate%20a%20logo%20for%20an%20adventure%20brand.png)

3. 现在，让我们通过在描述中添加更多细节来修改提示：

    ```A logo combining a tent silhouette and stars, with a rustic feel for an adventure brand.```

4. 再次选择 **Generate**，并比较结果。

    ![包含帐篷轮廓和星星的冒险品牌标志](../../../../lab/Workshop Instructions/Images/logo-with-stars.png)

### 最佳实践

为了使用 DALL-E 3 创建高效且准确的图像，请遵循以下最佳实践：

1. **清晰且描述性的提示**：编写清晰且详细的文本提示。描述越具体，DALL-E 3 越有可能生成与你请求相符的图像。包括主体、动作、环境、风格及任何重要细节。
2. **使用形容词**：使用形容词和副词来描述你希望图像传达的特质、情感和特点。这有助于更精准地匹配你的需求。
3. **细节与简洁的平衡**：虽然细节很重要，但过于复杂或矛盾的提示可能会使 AI 感到困惑，从而产生意外结果。确保你的描述既提供足够的上下文，又不过于繁琐。
4. **尝试不同风格**：如果你希望图像具有特定的美学风格，可以指定艺术风格或影响。例如，你可以要求生成一张艺术风格的图像。
5. **迭代方法**：第一次生成的图像可能并不完美。将其作为起点，根据输出逐步优化提示，逐步接近你想要的结果。
6. **长宽比和构图**：如果你对图像的构图或长宽比有偏好，请在提示中注明。例如，你可以请求一张横向图像或主体偏离中心的肖像。
7. **文化和上下文参考**：如果适用，可以加入文化或历史参考，为图像生成过程提供额外的上下文。
8. **负责任的 AI 考量**：注意提示的负责任 AI 方面。避免生成冒犯性、强化刻板印象或侵犯版权的图像。
9. **测试和学习**：尝试不同的提示，了解 DALL-E 3 如何解释各种描述。这一学习过程可以帮助你随着时间的推移提高提示的精准度。
10. **遵循指南**：在创建提示时遵守 OpenAI 的使用案例政策和内容指南。避免请求生成 OpenAI 内容政策中不允许的图像。

## 品牌吉祥物创作

在本次工作坊中，我们将利用 DALL-E 3 的功能为品牌吉祥物生成图像，重点探索不同主题，例如友好的动物、机器人或抽象人物。

我们还将测试 DALL-E 3 的不同参数，以探索生成图像的多样性。这些参数包括：

- **图像尺寸**：尝试不同尺寸（例如正方形、横向、纵向），以了解图像尺寸如何影响吉祥物在各种活动中的设计和可用性。
- **图像风格**：尝试不同风格，例如自然或鲜艳，看看哪种最符合品牌个性。
- **图像质量**：调整质量设置，生成适合打印的高分辨率图像或适合网络或社交媒体使用的低分辨率版本。尺寸可以是高清或标准。

1. 让我们从生成一个品牌吉祥物开始。可以参考以下提示：

```A friendly robot mascot with a smiling face, designed in a cartoon style.```

![友好的机器人吉祥物](../../../../lab/Workshop Instructions/Images/robot-mascot-friendly.png)

```A playful fox mascot with a colorful scarf, representing agility and creativity.```

```An abstract figure with geometric shapes, conveying innovation and technology.```

2. 在 playground 中，点击 _省略号图标_ 并导航到 Settings。
3. 在每个部分下点击 _下拉箭头_ 以更改参数。
4. 使用更新的设置再次尝试提示。

## 高级提示

现在我们已经看过一些基础提示，让我们尝试一些新的内容。

>[!alert] 确保系统消息为空。若有需要，可以简单点击 **Reset to Default** 将系统消息重置为默认值。

接下来，我们将尝试基于 gpt-4o-mini 生成的提示生成图像。

1. 返回到 **Chat Playground**。

2. 在 **System message** 下，清空 **Give the model instructions and context** 旁边的现有消息，将系统消息重置为默认值。

3. 在 **聊天框** 中，添加对我们希望创建图像的产品的详细描述，并将请求提交给模型。

```
Generate a prompt for DALL-E 3 from this product description:

The 3D Animated Office Space Design by CreativeSpaces offers a modern, interactive representation of a professional work environment. This design concept includes ergonomic furniture, open and collaborative workspaces, greenery for a touch of nature, and large windows to maximize natural light. The layout also incorporates meeting pods, hot desks, and breakout areas for different work modes. The office has a neutral color palette, with accents of green and blue to create a calming yet productive atmosphere.

The 3D Animated Office Space Design is intended for use by architects, interior designers, and companies looking to revamp their workspaces. It highlights the importance of balancing privacy with collaboration, including quiet zones for focused work and shared areas for team interactions. The space features modern materials like glass and wood, combined with innovative lighting solutions to enhance productivity and employee well-being.

Beyond its aesthetic appeal, the 3D Animated Office Space Design is designed with functionality in mind. It includes ample storage solutions, acoustic panels to reduce noise, and modular furniture that can be rearranged to suit different needs. The green walls and potted plants throughout the office create a refreshing environment that promotes creativity and reduces stress. The design is presented in a high-quality 3D animation, providing a realistic walkthrough that allows clients to visualize the space effectively.
```

4. 一旦收到响应，点击响应顶部的三点图标，然后点击 **Copy response to clipboard**。

![复制选项的图片](../../../../lab/Workshop Instructions/Images/ai-foundry-copy-response.png)

5. 返回到 **Images playground**，根据提示生成图像。

6. 在 Images playground 中，**确保在 Deployments 下选择了 'dall-e-3'**，然后将生成的提示粘贴到 **Prompt Box**。

7. 点击 **Generate**，观察生成的图像有多详细。

![3D 办公空间的图片](../../../../lab/Workshop Instructions/Images/_Create%20a%203D%20animation%20of%20a%20modern%20office%20space%20design%20featuring%20ergonomic%20furniture,%20collaborative%20workspaces,%20and%20greenery%20elements.%20The%20office%20should%20have%20large%20windows%20for%20natural%20light,%20meeting%20pods,%20an.png)

## 下一步

恭喜！你现在已经完成了实验室的第二部分，并为 Contoso Outdoors 公司的电子商务网站生成了所需的图像素材。在实验室的下一部分，你将学习如何将模型用于多模态请求。

前往 [第3部分：多模态交互](./04_Multimodal_Interfaces.md)

**免责声明**：  
本文件通过基于机器的人工智能翻译服务翻译而成。尽管我们努力确保准确性，但请注意，自动翻译可能包含错误或不准确之处。应以原始语言的文件作为权威来源。对于关键信息，建议使用专业的人类翻译服务。我们对因使用此翻译而引起的任何误解或误读不承担责任。