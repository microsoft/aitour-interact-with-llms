# 第四部分 - Azure AI Agents

歡迎來到本工作坊的第四部分！

到目前為止，我們已經以多種不同的方式與大型語言模型互動。然而，這些互動是孤立的，並且針對非常特定的用途。**Azure AI Agents** 代表了我們互動的下一步，因為它們幫助我們將之前的互動整合為一個解決方案。

> [!TIP]  
> **什麼是 Azure AI Agent？**  
> 它是一種完全託管的服務，旨在讓開發人員能夠安全地構建、部署和擴展高質量且可擴展的 AI Agent，而無需管理底層的計算和存儲資源。該服務整合了狀態管理、上下文關聯、聊天線程以及代碼執行等功能，從而更輕鬆地訪問第三方擴展功能。

以前，即使是經驗豐富的開發人員，構建自定義 AI Agent 也需要投入大量精力。雖然聊天完成 API 輕量且強大，但它本質上是無狀態的，這意味著開發人員需要手動管理對話狀態和聊天線程、工具集成、檢索文檔和索引，以及執行代碼。

在 Azure AI Foundry 中，AI Agent 作為一種「智能」微服務，可以用來回答問題（RAG）、執行操作，甚至完全自動化工作流程。它通過將生成式 AI 模型的能力與可訪問並與現實世界數據源交互的工具相結合來實現這一目標。

如果需要，Agents 還可以同時訪問多個工具。其中一些工具包括：
- **Function Calling**
- **Code Interpreter**
- **File Search**
- **Grounding with Bing Search**
- **Azure Functions** 等等。

在本節中，我們將介紹 Code Interpreter。

## 理解 Agent 的組成部分

要開始使用 Azure AI Agents，了解並處理其功能所涉及的不同組成部分非常重要。

正如我們現在所知，**Agent** 僅僅是一種「智能」微服務，可以通過 RAG 執行操作、自動化工作流程或回答問題。

創建 Agent 之後的下一步是創建一個 **Thread**。**Thread** 是 Agent 和用戶之間的一個對話會話。Threads 儲存消息並自動處理截斷，以便將內容適配到模型的上下文中。

**Messages** 是由 Agent 或用戶創建的，包含文本、圖像和其他文件。這些消息以列表形式存儲在 Thread 中。

最後，我們可以 **Run** Agent。這意味著啟動 Agent，根據 Thread 的內容開始運行。Agent 使用其配置和 *Thread 的 Messages* 通過調用模型和工具來執行任務。作為運行的一部分，Agent 會將 *Messages 附加到 Thread*。

## 創建 Agent

1. 在左側導航欄的 _Build and customize_ 下，選擇 **Agents**。在新打開的頁面中，點擊下拉箭頭選擇你的 Azure OpenAI Service 資源，然後選擇 **Let's go** 按鈕。

![選擇 Azure OpenAI Service 資源的截圖](../../../../lab/Workshop Instructions/Images/agents-aoai-select.jpeg)

2. 系統會為你創建一個新的 Agent。在 **Deployments** 區域，確保選擇 **gpt-4o-mini** 模型。

    > [!TIP]  
    > **確保選擇了正確的部署。** 它應顯示為 **gpt-4o-mini** 以及其版本。

3. 接下來，為 Agent 命名。在 Agent Name 文本框中輸入以下內容：

    ```Contoso Outdoor Sales Agent```

4. 然後，我們可以為 Agent 提供一個 **instruction**。這類似於我們在之前部分中看到的 *System Message*，為 Agent 提供需要遵循的目標。導航到 **Prompt** 標籤，並將以下指令複製到指令文本框中。

    ``` 
    You are a sales Agent for Contoso Outdoor. You are polite, professional, helpful and friendly.

    You get all the sales data from the uploaded .csv files. There is sales revenue data that is broken down by region, product category, product type and separated by year and month.

    Examples of regions include Africa, Asia, Europe and America. Categories include climbing gear, camping equipment, apparel and others. Product categories include jackets, hammocks, wet suits, shoes and more. 

    If a question is not related to sales or you cannot answer the question, you **must** respond: "Please contact IT for more assistance". If the user asks for help or says 'help', provide a list of sample questions that you can answer.
    ```

    ![Agents Playground](../../../../lab/Workshop Instructions/Images/agents-playground-update-details.jpeg)

    > [!NOTE]  
    > 你能從這個 prompt 中識別出多少前面部分提到的 prompt 工程技術？提示請參考工作坊的第二部分。

5. 導航到 **Actions** 標籤，然後點擊 **add**。

    ![Agent 添加新文件](../../../../lab/Workshop Instructions/Images/agents-actions.jpeg)

6. 新標籤頁中，選擇 **Code interpreter**。

7. 在下一個窗口中，點擊 **select local files**，選擇 `Contoso_Sales_Revenue.csv` file on your Desktop.
    ![Agents code interpreter](../../../../lab/Workshop Instructions/Images/aifoundry-codeinterpreter-upload-file.jpeg)

    >[!NOTE]
    > If you cannot find the file on your desktop, you can download it from [here](../../../../lab/Workshop Instructions/assets/Contoso_Sales_Revenue.csv).

7. Click on the **upload and add** button. You should now see the file under the *Code Interpreter* tool.

The Agent is now ready for us to interact with it.

## Interacting with our Agent

1. On the top right of our Agents window, select **Try in playground**

![](../../../../lab/Workshop Instructions/Images/agents-try-in-playground.jpeg)

2.  Let's begin by typing `help`，並在聊天框中確認。你會注意到這會開始一個新 Thread。  
   你還會看到一系列範例問題供測試。測試其中一個問題，觀察 Agent 的回覆！

8. 接下來，我們嘗試一個具體的查詢。輸入以下內容：

    ```What are the total sales for Europe broken down by category? ```

    你會注意到 Agent 使用 Code Interpreter 為你提供答案。

9. 現在，我們嘗試處理這些數據。輸入以下提示：

    ```Put this data in a graph. ```

    通過 Code Interpreter，Agent 能夠將結構化數據轉換為圖表！

10. 如果你想查看另一種類型的圖表，可以嘗試以下提示，並請求數據以圖表形式呈現：

    ```What is the trending product category? Give the output as a graph. ```

    Agent 應該通過分析銷售收入數據隨時間的變化，為你生成一個展示熱門產品趨勢的圖表。

恭喜！你現在已經完成了工作坊的最後部分，並學習了什麼是 Azure OpenAI Assistants，它們如何運作以及如何使用 Azure AI Studio 創建它們。

前往工作坊的最後部分：[總結](./07_Summary.md)

**免責聲明**：  
本文件使用基於機器的人工智能翻譯服務進行翻譯。儘管我們努力確保準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。應以原文文件為權威來源。對於關鍵信息，建議尋求專業人工翻譯。我們對因使用此翻譯而引起的任何誤解或錯誤解釋概不負責。