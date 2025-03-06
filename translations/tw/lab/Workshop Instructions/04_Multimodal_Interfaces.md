# 第三部分 - 多模態

到目前為止，我們僅使用單一模態與 LLMs 互動：輸入文字並接收文字或圖片作為回應。然而，多模態介面正變得越來越受歡迎，因為它們允許用戶透過多種模態（如文字、圖片和語音）與模型互動，從而提升人機互動的體驗。在本節中，我們將探索如何使用多模態介面與 **GPT-4o mini** 和 **GPT-4o audio** 進行互動。

> [!TIP]  
> **GPT-4o mini** 是一個多模態模型，結合了自然語言處理與視覺理解。它能夠處理文字與圖片的組合輸入，並生成與這兩種模態相關的輸出。

**GPT-4o realtime** 支援低延遲的「語音輸入、語音輸出」對話式互動，非常適合用於需要即時互動的場景，例如客服代理、語音助理和即時翻譯器。

## 最佳實踐

- **情境具體性**：為當前場景添加上下文，可以幫助模型更好地理解並生成適合的輸出。這種具體性有助於專注於相關細節，避免無關資訊。  

- **任務導向提示**：聚焦於特定任務，有助於模型從該角度生成輸出。  

- **定義輸出格式**：清楚說明所需的輸出格式，例如 markdown、JSON、HTML 等。您也可以建議特定的結構、長度或回應的具體屬性。  

- **處理拒絕**：當模型表示無法執行某項任務時，調整提示是一個有效的解決方案。更具體的提示可以幫助模型更清楚地理解並更好地執行任務。以下是一些提示：  
    - 要求模型對生成的回應進行解釋，以提高輸出的透明度  
    - 如果使用單張圖片作為提示，將圖片放在文字之前  
    - 要求模型先詳細描述圖片，然後根據描述完成您的特定任務  

- **提示調整**：嘗試我們在文字生成場景中探索過的提示調整技巧，例如：  
    - 將請求分解（例如，思路鏈式）  
    - 添加範例（例如，少樣本學習）  

## 使用圖片與模型互動

1. 前往 **playgrounds** 區域並選擇 **Try the Chat Playground**

> [!alert] 開始之前，點擊 **Clear Chat** 清除先前互動的上下文。

2. 在聊天文字框中，點擊附件圖示上傳本地圖片。

![上傳圖片作為輸入](../../../../lab/Workshop Instructions/Images/upload_image_icon.png)

3. 選取桌面上 ```house-multimodal``` 資料夾中的所有圖片。  
4. 上傳文件後，嘗試以下提示以開始與圖片互動：

```
Create a tagline and short description for this rental home advertisement.
- The first picture is from the home
- The other pictures are from sights nearby
- In the description use the features of the house and make the ad more compelling with the sights. 
- Do not talk about features not visible in the images.
- If you have information about the location of the images, use that information in the description
```

## 提供上下文

在下一個演示中，我們有一張被遮擋的圖片。圖片中故意添加了邊框以遮擋完整的上下文。

1. _清除聊天_，然後在聊天文字框中添加以下提示：``what is that?``  
2. 點擊附件圖示，前往桌面資料夾，並上傳 [context-001](./Images/context-001.png) 圖片並發送提示。

> 如果我問「嘿，這是什麼？」您可能會很難辨認這段文字。這展示了光學字符識別中的一個經典計算機視覺挑戰：解讀模糊、孤立的文字。現在，如果我使用 gpt-4o-mini 並問它「這是什麼？」它會回答：「由於手寫風格，文字不太清晰可讀。可能是 'Mark'。」更有趣的是，它還補充道：「部分文字似乎被遮擋，無法讀取。」

3. 我們將新增一張圖片，前往桌面資料夾，並上傳 [context-002](./Images/context-002.png) 圖片到聊天中，並輸入提示 ```Extract all the texts from the image. Explain what you think this is.```

> 顯示更多內容後，辨認它仍然相當具有挑戰性。這次，提示稍作調整為：「從圖片中提取所有文字。解釋您認為這是什麼。」gpt-4o-mini 回答：「這上面寫著 'milk, steak'，看起來像是一張購物清單。」它還指出圖片仍然部分被遮擋，這非常有趣。

4. 我們將新增最後一張圖片，前往桌面資料夾，並上傳 [context-003](./Images/demo-4-context-003.png) 圖片到聊天中，並輸入提示：```Extract all the texts from the image. Explain what you think this is.```

> 完整顯示圖片後，我們發現 gpt-4o-mini 是正確的——這確實是一張購物清單。它準確地識別出像是「mayo」和「organic bread」這樣的項目。更有趣的是，它對底部備註的解讀。它捕捉到了細微的上下文，指出：「啤酒項目的備註似乎在提醒或強調節制或限制數量。」

## 即時語音互動

透過整合 **gpt-4o-realtime-preview** 模型，用戶可以使用語音命令與平台互動，使購物體驗更加有趣且便利。

1. 回到 **Playgrounds** 並選擇 **try Real-time audio playground**，將部署設置為 **gpt-4o-realtime-preview**  

2. 在 **model instructions box** 中更新以下內容：

    ```You are a pirate, and every response must be full of pirate lingo. ```

3. 在 playground 中，點擊 **enable microphone**，會彈出一個視窗，點擊允許以啟用語音互動。

![啟用 AI Foundry 中的語音](../../../../lab/Workshop Instructions/Images/aifoundry-enable-audio.jpeg)

4. 點擊 **start listening** 按鈕，說出 ``hello`` 並詢問模型一些事實。

5. 接著，將系統訊息的語氣更改如下，再次與模型互動：

```You are a valiant medieval knight. Every response should echo the chivalry, honor, and grandeur of the court. Speak with formality and grace, as if addressing kings, queens, and noble warriors.```

## 下一步

恭喜您！您已完成實驗室的第三部分，並學會了如何與多模態模型互動。

繼續前往 [第四部分：Azure AI Agents](./05_AI_Agents.md)

**免責聲明**：  
本文件已使用基於機器的人工智能翻譯服務進行翻譯。儘管我們努力確保翻譯準確，但請注意，自動翻譯可能包含錯誤或不準確之處。應以原文作為權威來源。對於關鍵信息，建議尋求專業人工翻譯。我們對因使用本翻譯而引起的任何誤解或誤讀不承擔責任。