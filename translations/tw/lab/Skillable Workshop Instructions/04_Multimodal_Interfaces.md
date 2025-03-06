# 第三部分 - 多模態

到目前為止，我們僅使用單一模態與大型語言模型（LLMs）進行互動：輸入文字並接收文字或圖片作為回應。然而，多模態介面越來越受歡迎，因為它們允許使用者通過多種模態（如文字、圖片和語音）與模型互動，從而改善人機互動體驗。在本節中，我們將探索如何使用多模態介面與 **GPT-4o mini** 和 **GPT-4o audio** 互動。

> [!TIP]  
> **GPT-4o mini** 是一種結合自然語言處理與視覺理解的多模態模型。它能夠處理文字與圖片的組合作為輸入，並生成與兩種模態相關的輸出。

**GPT-4o realtime** 支援低延遲的「語音輸入、語音輸出」對話式互動。這非常適合用於需要即時互動的場景，例如客戶支持代理、語音助手和即時翻譯。

## 最佳實踐

- **情境具體性**：為當前場景添加上下文可以讓模型更好地理解適當的輸出。這種具體性有助於聚焦於相關細節並避免多餘的資訊。

- **任務導向提示**：聚焦於特定任務的提示可以幫助模型從該角度生成輸出。

- **定義輸出格式**：明確說明所需的輸出格式，例如 markdown、JSON、HTML 等。您還可以建議特定的結構、長度或輸出內容的特定屬性。

- **處理拒絕**：當模型表示無法完成某項任務時，改進提示可能是一個有效的解決方案。更具體的提示可以引導模型更清楚地理解並更好地執行任務。一些需要注意的提示：  
  - 要求模型對生成的回應進行解釋，以增強輸出的透明度  
  - 如果使用單一圖片作為提示，將圖片放在文字之前  
  - 要求模型先詳細描述圖片內容，然後從描述中完成您的特定任務  

- **提示調整**：嘗試我們在文字生成場景中探索過的提示調整技術，例如：  
  - 將請求分解（例如，連鎖思維）  
  - 添加範例（例如，少樣本學習）  

## 使用圖片與模型互動

1. 前往 **playgrounds** 區域並選擇 **Try the Chat Playground**

>[!alert] 在開始之前，點擊 **Clear Chat** 以避免受之前互動的上下文影響。

2. 在聊天文字框中，點擊附件圖示以上傳本地圖片。

![將圖片作為輸入上傳](../../../../lab/Skillable Workshop Instructions/Images/upload_image_icon.png)

3. 從桌面上的 ```house-multimodal``` 資料夾中選擇所有圖片。  
4. 上傳檔案後，嘗試以下提示開始與圖片互動：

```
Create a tagline and short description for this rental home advertisement.
- The first picture is from the home
- The other pictures are from sights nearby
- In the description use the features of the house and make the ad more compelling with the sights. 
- Do not talk about features not visible in the images.
- If you have information about the location of the images, use that information in the description
```

## 提供上下文

在接下來的演示中，我們將使用一張受遮擋的圖片。圖片中故意添加了邊界框來遮蔽完整的上下文。

1. **清除聊天**，然後在聊天文字框中添加提示：``what is that?``  
2. 點擊附件圖示，進入桌面資料夾並上傳 [context-001](./Images/context-001.png) 圖片，然後發送提示。

> 如果我問您「嘿，這是什麼？」您可能會難以辨認這段文字。這展示了一個經典的電腦視覺挑戰：在光學字符識別中解讀模糊、孤立的文字。現在，如果我使用 gpt-4o-mini 並問「這是什麼？」它回應道：「由於手寫風格，文字無法清楚辨認。可能是 'Mark'。」值得注意的是，它還提到「部分文字似乎被遮擋，無法讀取。」

3. 我們將添加一張新圖片，進入桌面資料夾並上傳 [context-002](./Images/context-002.png) 圖片到聊天中，並使用提示 ```Extract all the texts from the image. Explain what you think this is.```

> 再揭示多一些內容後，仍然很難辨認這是什麼。這次，提示稍作調整為：「從圖片中提取所有文字。解釋您認為這是什麼。」gpt-4o-mini 回應道：「這寫著 'milk, steak'，看起來像是一張購物清單。」它還提到圖片仍然部分被遮擋，這非常有趣。

4. 我們將添加最後一張圖片，進入桌面資料夾並上傳 [context-003](./Images/demo-4-context-003.png) 圖片到聊天中，並使用提示：```Extract all the texts from the image. Explain what you think this is.```

> 當完整圖片顯示後，我們發現 gpt-4o-mini 是正確的——這確實是一張購物清單。它準確地辨認出「mayo」和「organic bread」等項目。更有趣的是，它還解讀了底部的備註，指出「關於啤酒項目的備註似乎是一個提醒，或者是對節制或限制數量的強調。」

## 即時語音互動

通過整合 **gpt-4o-realtime-preview** 模型，用戶可以使用語音指令與平台互動，使購物體驗更加有趣且易於訪問。

1. 返回 **Playgrounds**，選擇 **try Real-time audio playground**，並將部署設置為 **gpt-4o-realtime-preview**

2. 在 **model instructions box** 中更新以下內容：

    ```You are a pirate, and every response must be full of pirate lingo. ```

3. 在 playground 中，點擊 **enable microphone**，會彈出一個窗口，點擊允許以啟用語音互動。

![在 AI Foundry 中啟用語音](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-enable-audio.jpeg)

4. 點擊 **start listening** 按鈕，說出 ``hello`` 並詢問模型一些事實。

5. 接著，修改系統訊息的語氣如下，然後再次與模型互動：

```You are a valiant medieval knight. Every response should echo the chivalry, honor, and grandeur of the court. Speak with formality and grace, as if addressing kings, queens, and noble warriors.```

## 下一步

恭喜！您已完成實驗的第三部分，並學會如何與多模態模型互動。

點擊 **Next** 前往 Azure AI Agents 部分。

**免責聲明**：  
本文件是使用機器翻譯服務進行翻譯的。雖然我們努力確保準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。應以原文檔的母語版本作為權威來源。對於關鍵信息，建議尋求專業人工翻譯。我們對因使用此翻譯而引起的任何誤解或誤讀概不負責。