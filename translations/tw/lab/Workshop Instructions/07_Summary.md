# 摘要
做得好！你完成了這次工作坊，並成功為 Contoso Outdoor Company 設計了一個電商網站，充分利用了生成式 AI 的強大功能。

## 清理資源

完成教學後，您可能需要刪除所有創建的資源。您可以單獨刪除資源，也可以刪除整個資源群組。

1. 瀏覽至 [Azure Portal](https://portal.azure.com)。  
2. 從首頁導航到 **資源群組**，然後選擇我們創建的資源群組：**interact-with-llms**。

![](../../../../lab/Workshop Instructions/Images/azure-portal-resource-group.PNG)

3. 在資源群組的頂部導航欄中，選擇 **刪除資源群組**。

![](../../../../lab/Workshop Instructions/Images/delete-resource-group-navigation.PNG)

4. 系統會提示您輸入資源群組名稱以確認刪除。輸入名稱 **interact-with-llms**，然後點擊 **刪除** 以刪除您的資源群組。

![刪除資源群組](../../../../lab/Workshop Instructions/Images/delete-resource-group-name.PNG)

5. 您將收到資源群組已刪除的通知。

![](../../../../lab/Workshop Instructions/Images/delete-resource-group-notification-popup.PNG)

## 一些關鍵要點
- 生成式 AI 模型可以生成類似人類的文本、圖像和代碼。
- 生成式 AI 模型是無狀態的：它們不會學習，並受到其訓練數據的限制，該數據在某個固定時間點被凍結。
- Azure OpenAI Service 是一項託管服務，提供對最先進的自然語言生成式 AI 模型的訪問，包括來自 OpenAI 的 GPT-4、GPT-4 turbo 和 GPT-4o，並具備 Azure 的安全性和企業承諾。
- Azure AI Foundry 是 Azure 的統一 AI 平台，包含 Azure AI 入口網站和統一的 SDK 體驗，此外還有預構建的應用模板以及對第三方 ISV 工具和服務的訪問。
- Prompt engineering 是一種用於“基礎化”生成式 AI 模型的技術，可用於影響模型輸出的風格、提供事實信息以及限制非預期行為。
- Azure AI Agents 是一項新功能，使開發者能更輕鬆地創建具有複雜類似助理體驗的應用程序，這些應用程序可以篩選數據、建議解決方案並通過整合工具自動化任務。

## 其他資源
以下是一些資源，幫助您更進一步了解 Azure OpenAI Service 和 Azure AI Foundry：

- Microsoft Learn 模組：[Azure OpenAI Service 簡介](https://learn.microsoft.com/en-us/training/modules/explore-azure-openai/?WT.mc_id=aiml-132569-cacaste)
- [Azure OpenAI Service 文件](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/?WT.mc_id=aiml-132569-cacaste)
- [Azure OpenAI Service 價格](https://azure.microsoft.com/en-us/products/cognitive-services/openai-service/#pricing/?WT.mc_id=aiml-132569-cacaste)
- [Azure OpenAI Service 透明度說明](https://learn.microsoft.com/en-us/legal/cognitive-services/openai/transparency-note/?WT.mc_id=aiml-132569-cacaste) 提供了 Azure OpenAI 模型的功能、使用案例和限制的詳細資訊。
- [開始使用 Azure AI Foundry 並實現 RAG 模式](https://learn.microsoft.com/training/paths/create-custom-copilots-ai-studio//?WT.mc_id=aiml-132569-cacaste)
- [開始使用 Azure AI Agents](https://learn.microsoft.com/en-us/azure/ai-services/agents/overview)

**免責聲明**：  
本文件已使用機器翻譯服務進行翻譯。我們雖然努力確保準確性，但請注意，自動翻譯可能會包含錯誤或不準確之處。應以原文文件為權威來源。對於關鍵資訊，建議尋求專業人工翻譯。我們對於因使用此翻譯而產生的任何誤解或錯誤解釋概不負責。