# 第 2 部分：圖像生成

歡迎來到本次工作坊的第二部分，我們將與文字轉圖像模型 DALL-E 3 進行互動。

> [!TIP]  
> 什麼是 DALL-E 3？DALL-E 3 是一種基於神經網絡的模型，可以根據**自然語言輸入**生成圖像數據。簡單來說，您只需提供 DALL-E 3 一個**描述**，它就能生成一張相應的圖像。

## 創建您的第一張圖像

按照以下步驟來創建您的第一張圖像：

![展示圖像生成的圖片](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-image-generation.jpeg)

1. 在左側導航欄中，進入 **playgrounds**，然後選擇 **Try the Image Playground**。
2. 在 Images playground 中，找到並點擊標有 **Deployments** 的下拉菜單。在下拉列表中選擇 **dall-e-3**。
3. 在 Images playground 中，找到標有 _"Describe the image you want to create."_ 的文本框。從下面的提示示例中點擊 "T"（例如 ``here is a sample prompt``），這將自動將該內容輸入到當前光標位置。
4. 輸入您的描述後，會出現一個 **Generate** 按鈕。點擊按鈕提交您的圖像描述給模型部署。
5. 發送查詢後，稍等片刻讓模型處理並響應。響應結果將顯示在輸入框下方的窗口中。

讓我們從在描述框中輸入一個基本提示並點擊生成開始：

```a watercolor painting of Chicago skyline```

這將生成如下所示的內容：

![水彩風格的天際線圖片](../../../../lab/Skillable Workshop Instructions/Images/DALL·E%202024-11-14%2009.27.57%20-%20A%20watercolor%20painting%20of%20the%20Chicago%20skyline,%20showcasing%20iconic%20skyscrapers%20such%20as%20the%20Willis%20Tower%20and%20John%20Hancock%20Center.%20The%20city%20is%20bathed%20in%20so.webp)

DALL-E 3 生成的圖像是原創的；它們並非來自某個策劃好的圖像庫。換句話說，DALL-E 3 並不是用來搜尋合適圖片的系統，而是一個基於其訓練數據生成全新圖像的人工智能 (AI) 模型。

### 提供具體描述

細節可以讓生成的結果更加準確。與文字生成類似，圖像生成模型非常依賴於您對所需圖像的詳細描述。

1. 例如，輸入以下提示：

    ```A logo for an adventure brand```

2. 然後選擇 **Generate** 並查看生成的圖像。

    ![冒險品牌的標誌圖片](../../../../lab/Skillable Workshop Instructions/Images/Generate%20a%20logo%20for%20an%20adventure%20brand.png)

3. 現在，讓我們通過在描述中添加更多細節來修改提示：

    ```A logo combining a tent silhouette and stars, with a rustic feel for an adventure brand.```

4. 再次選擇 **Generate** 並比較結果。

    ![結合帳篷輪廓和星星的標誌圖片，具有冒險品牌的質樸感。](../../../../lab/Skillable Workshop Instructions/Images/logo-with-stars.png)

### 最佳實踐

為了使用 DALL-E 3 創建高效且準確的圖像，以下是一些最佳實踐：

1. **清晰且具描述性的提示**：編寫清晰且詳細的文本提示。描述越具體，DALL-E 3 越有可能生成符合您需求的圖像。包括主題、動作、環境、風格以及任何重要細節。
2. **使用形容詞**：使用形容詞和副詞來描述您希望圖像傳達的特質、情感和特徵。這有助於更精確地匹配您的構想。
3. **細節與簡潔的平衡**：雖然細節很重要，但過於複雜或矛盾的提示可能會讓 AI 感到困惑，導致意料之外的結果。力求在提供足夠上下文的同時保持簡潔。
4. **嘗試不同風格**：如果希望圖像具有特定的美學風格，可以指定藝術風格或影響。例如，您可以要求生成一張藝術風格的圖像。
5. **迭代方法**：通常，第一次生成的圖像可能並不完美。將其作為起點，根據輸出迭代修改提示，逐步接近您的理想結果。
6. **比例和構圖**：如果您對圖像的構圖或比例有偏好，可以在提示中說明。例如，您可以請求橫向圖像或主體偏離中心的肖像。
7. **文化和上下文參考**：如果適用，加入文化或歷史參考，以提供額外的上下文，幫助引導圖像生成過程。
8. **負責任的 AI 使用考量**：謹慎考慮您的提示可能帶來的影響。避免創建具有冒犯性、強化刻板印象或侵犯版權的圖像。
9. **測試與學習**：嘗試不同的提示，了解 DALL-E 3 如何解讀各種描述。這一學習過程能幫助您逐步提高提示的精確性。
10. **遵循指導方針**：在創建提示時，遵守 OpenAI 的使用案例政策和內容指導方針。避免請求不符合 OpenAI 內容政策的圖像。

## 品牌吉祥物創作

在本次工作坊中，我們將利用 DALL-E 3 的功能生成品牌吉祥物的圖像，重點關注不同主題，如友善的動物、機器人或抽象形象。

我們還將測試 DALL-E 3 的不同參數，以探索生成圖像的多樣性。這些參數包括：

- **圖像尺寸**：嘗試不同尺寸（例如正方形、橫向、縱向），了解圖像尺寸如何影響設計和吉祥物在各種活動中的適用性。
- **圖像風格**：嘗試不同風格，如自然或鮮豔，看看哪種最符合品牌的個性。
- **圖像質量**：調整質量設置，以生成適合印刷的高分辨率圖像或適合網頁或社交媒體使用的低分辨率版本。尺寸可以是高清或標準。

1. 讓我們開始生成一個品牌吉祥物。可以考慮以下提示：

```A friendly robot mascot with a smiling face, designed in a cartoon style.```

![友善機器人吉祥物的圖片](../../../../lab/Skillable Workshop Instructions/Images/robot-mascot-friendly.png)

```A playful fox mascot with a colorful scarf, representing agility and creativity.```

```An abstract figure with geometric shapes, conveying innovation and technology.```

2. 在 playground 中，點擊 _省略號圖標_ 並進入 Settings。
3. 在每個部分下，點擊 _下拉箭頭_ 以更改參數。
4. 使用更新的設置再次嘗試提示。

## 高級提示設置

現在我們已經看過一些基本提示，讓我們嘗試一些新內容。

>[!alert] 確保系統消息為空。您可以簡單點擊 **Reset to Default** 來重置系統消息為默認。

我們將嘗試基於 gpt-4o-mini 生成的提示創建圖像。

1. 返回 **Chat Playground**。

2. 在 **System message** 下，清除 **Give the model instructions and context** 旁邊的現有消息，將系統消息重置為默認。

3. 在 **chat box** 中，添加我們希望創建圖像的產品的詳細描述，並將請求提交給模型。

```
Generate a prompt for DALL-E 3 from this product description:

The 3D Animated Office Space Design by CreativeSpaces offers a modern, interactive representation of a professional work environment. This design concept includes ergonomic furniture, open and collaborative workspaces, greenery for a touch of nature, and large windows to maximize natural light. The layout also incorporates meeting pods, hot desks, and breakout areas for different work modes. The office has a neutral color palette, with accents of green and blue to create a calming yet productive atmosphere.

The 3D Animated Office Space Design is intended for use by architects, interior designers, and companies looking to revamp their workspaces. It highlights the importance of balancing privacy with collaboration, including quiet zones for focused work and shared areas for team interactions. The space features modern materials like glass and wood, combined with innovative lighting solutions to enhance productivity and employee well-being.

Beyond its aesthetic appeal, the 3D Animated Office Space Design is designed with functionality in mind. It includes ample storage solutions, acoustic panels to reduce noise, and modular furniture that can be rearranged to suit different needs. The green walls and potted plants throughout the office create a refreshing environment that promotes creativity and reduces stress. The design is presented in a high-quality 3D animation, providing a realistic walkthrough that allows clients to visualize the space effectively.
```

4. 獲得響應後，點擊響應頂部的三點圖標，然後點擊 **Copy response to clipboard**。

![複製選項的圖片](../../../../lab/Skillable Workshop Instructions/Images/ai-foundry-copy-response.png)

5. 返回 **Images playground**，以生成提示響應中的圖像。

6. 在 Images playground 中，**確保 'dall-e-3' 已在 Deployments 下選中**，然後將生成的提示粘貼到 **Prompt Box**。

7. 點擊 **Generate**，並注意圖像的細緻程度。

![3D 工作空間的圖片](../../../../lab/Skillable Workshop Instructions/Images/_Create%20a%203D%20animation%20of%20a%20modern%20office%20space%20design%20featuring%20ergonomic%20furniture,%20collaborative%20workspaces,%20and%20greenery%20elements.%20The%20office%20should%20have%20large%20windows%20for%20natural%20light,%20meeting%20pods,%20an.png)

## 下一步

恭喜！您已完成實驗室的第二部分，並生成了不同的圖像資產。在實驗室的下一部分，您將學習如何使用該模型進行多模態請求。

點擊 **Next** 以進入多模態部分。

**免責聲明**：  
本文件使用機器翻譯服務進行翻譯。我們雖然努力確保準確性，但請注意，自動翻譯可能包含錯誤或不精確之處。應以原語言的文件作為權威來源。如涉及關鍵信息，建議尋求專業人工翻譯。我們對因使用本翻譯而引起的任何誤解或錯誤解讀概不負責。