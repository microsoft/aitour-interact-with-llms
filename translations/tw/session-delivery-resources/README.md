## 如何使用

歡迎加入，

> 以下資源是為了幫助講者學習並傳遞這場課程而設計的。

很高興你能參與這次的內容傳遞。我們相信作為一位有經驗的講者，你已經知道如何進行演講，因此本指南將重點放在你需要呈現的內容上。這份指南將帶你完整了解由簡報設計團隊製作的內容。

除了簡報的影片之外，本文件還會連結到所有你需要的資源，包括 PowerPoint 投影片以及示範指導與程式碼。

1. 通讀整份文件。
<!-- 1. 觀看簡報影片 -->
1. 向主講者提出問題。

## 文件摘要

| 資源                | 連結                              | 描述         |
|-------------------|----------------------------------|-------------------|
| PowerPoint        | [Presentation](https://aka.ms/AAryqzi) | 投影片 |
| Session Delivery Resources PPT 錄影     | [Video](https://aka.ms/AAs7etz) | Session Delivery Resources PowerPoint 投影片的錄製版本 |
| Session Delivery Resources PowerPoint |  [Deck](https://aka.ms/AAs7mfu) | 本工作坊的 Session Delivery Resources 投影片 |
| Workshop 指導文件 |  [Video](/lab/Workshop%20Instructions/00_Introduction.md) | 與 LLMs 互動的逐步指導 |
| Skillable Workshop 指導文件 |  [Video](/lab/Skillable%20Workshop%20Instructions/00_Introduction.md) | Skillable 實驗室指導文件 |

## 開始使用

此存放庫分為以下幾個部分：

| [Slides](https://aka.ms/AAryqzi) | [Skillable Workshop 指導文件](/lab/Skillable%20Workshop%20Instructions/00_Introduction.md) | [非 Skillable Workshop 指導文件](/lab/Workshop%20Instructions/00_Introduction.md) | 
|-------------------|---------------------------|--------------------------------------
| 35 張投影片  | 4 個部分 - 15 分鐘 | [在非 Skillable 環境中執行工作坊](/lab/Workshop%20Instructions/00_Introduction.md) |

## 投影片

[投影片](https://aka.ms/AAryqzi) 每部分都包含講者備註。

### 時間安排

> [NOTE!]
> 工作坊的 Q&A 通常會在進行中進行。可以考慮將這 5 分鐘挪作更實際操作的時間。

| 時間        | 描述 
--------------|-------------
0:00 - 3:00   | 課程介紹 
3:00 - 15:00  | 大型語言模型如何運作？ 
15:00 - 30:00 | 文本生成
30:00 - 45:00 | 圖像生成與多模態
45:00 - 65:00 | Azure AI 助理
70:00 - 75:00 | 課程重點總結

### 工作坊傳遞格式

- 在本工作坊中，前 15 分鐘專注於講解投影片內容，說明 LLMs 的運作方式。 
- 剩餘時間讓參與者個別進行工作坊內容，並在需要時提供協助。
- 最後，分享結尾投影片並總結課程。

## Skillable 工作坊指導文件

[你可以在這裡獲得關於工具的概覽以及我們如何使用它們的高層次介紹](/lab/Skillable%20Workshop%20Instructions/01_Set_up.md)。

| 部分 | 時間 | 
-------------------------------------------------------------------------------------------------------|---------|
|  [1 - 介紹 Azure AI Foundry](/lab/Skillable%20Workshop%20Instructions/01_Set_up.md) | 10       | 
|  [2 - 文本生成](/lab/Skillable%20Workshop%20Instructions/02_Text_Generation.md) | 15   |
|  [3 - 圖像生成](/lab/Skillable%20Workshop%20Instructions/03_Image_Generation.md) | 10   | [Link](../../../session-delivery-resources) | 15       | 
|  [4 - 多模態](/lab/Skillable%20Workshop%20Instructions/04_Multimodal_Interfaces.md) | 10  | 
|  [5 - AI 助理](/lab/Skillable%20Workshop%20Instructions/05_AI_Assistants.md) | 15  | [Link](../../../session-delivery-resources)  |

## 在非 Skillable 環境中執行工作坊

若要在無 Skillable 訪問的情況下進行本課程，請確保聽眾在完成實驗時符合以下要求：

- 一個 Azure 訂閱 - [免費創建一個。](https://azure.microsoft.com/free/cognitive-services?WT.mc_id=aiml-132569-bethanycheum)
- 一個支持 GPT-4o 和 DALL.E 3 模型的 Azure OpenAI 資源，且位於支持的區域內。[了解更多](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models#assistants-preview?WT.mc_id=aiml-132569-bethanycheum)。建議的區域為 **瑞典中部**。

要將資源部署到 Azure，只需點擊 **部署到 Azure** 按鈕。

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2Faitour-interact-with-llms%2Fmain%2Flab%2FWorkshop%20Instructions%2Fassets%2FAITour24_WKR540_Template.json)

所有工作坊指導文件可在[這裡找到](/lab/Workshop%20Instructions/00_Introduction.md)。

**免責聲明**：  
本文檔係使用基於機器的人工智能翻譯服務進行翻譯。我們致力於追求準確性，但請注意，自動翻譯可能會包含錯誤或不準確之處。應以原文檔的母語版本作為權威來源。對於關鍵資訊，建議使用專業人工翻譯。我們對因使用此翻譯而產生的任何誤解或錯誤解讀概不負責。