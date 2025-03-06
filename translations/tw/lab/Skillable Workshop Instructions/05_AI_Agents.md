# 第四部分 - Azure AI Agents

歡迎來到本工作坊的第四部分！

到目前為止，我們已經以多種不同的方式與大型語言模型進行了互動。然而，這些互動通常是孤立的，並且侷限於特定的用途。**Azure AI Agents** 代表了我們互動的下一步，因為它們幫助我們將之前的互動整合到一個解決方案中。

> [!TIP]  
> **什麼是 Azure AI Agent？**  
> 這是一項完全託管的服務，旨在幫助開發者安全地構建、部署和擴展高品質且可擴展的 AI Agents，而無需管理底層的計算和存儲資源。它整合了狀態管理、上下文關聯、聊天線程和代碼執行等功能，從而更容易訪問第三方擴展功能。

過去，構建自定義 AI Agents 即使對於經驗豐富的開發者來說也需要大量的工作。雖然聊天補全 API 輕量且強大，但它本質上是無狀態的，這意味著開發者需要手動管理對話狀態和聊天線程、工具整合、文件檢索和索引，以及執行代碼。

在 Azure AI Foundry 中，AI Agent 作為一個「智能」微服務，可以用於回答問題（RAG）、執行操作或完全自動化工作流程。它通過結合生成式 AI 模型的力量和工具來實現這一點，從而使其能夠訪問並與現實世界的數據源互動。

如果需要，Agents 還可以同時訪問多個工具。其中一些工具包括：
- **函數調用**
- **代碼解釋器**
- **文件搜索**
- **使用 Bing 搜索進行基礎查詢**
- **Azure Functions** 等等。

在本節中，我們將探討代碼解釋器。

## 理解 Agents 的組成部分

開始使用 Azure AI Agents 前，我們需要了解並處理其功能中涉及的不同組成部分。

如我們所知，**Agent** 只是個能夠執行操作、自動化工作流程或通過 RAG 回答問題的「智能」微服務。

創建 Agent 後的下一步是建立一個 **Thread**。**Thread** 是 Agent 與用戶之間的對話會話。Threads 存儲訊息，並自動處理截斷以適應模型的上下文。

**訊息** 則由 Agent 或用戶創建，包括文字、圖片和其他文件。這些訊息以列表的形式存儲在 Thread 中。

最後，我們可以 **執行** Agent。這意味著啟動 Agent，根據 Thread 的內容開始運行。Agent 使用其配置和 *Thread 的訊息*，通過調用模型和工具來執行任務。在執行過程中，Agent 會將訊息附加到 Thread 中。

## 創建 Agent

1. 在左側導航欄的 _Build and customize_ 下，選擇 **Agents**。在新打開的頁面中，點擊下拉箭頭選擇你的 Azure OpenAI Service 資源，然後選擇 **Let's go** 按鈕。

![選擇 Azure OpenAI Service 資源的截圖](../../../../lab/Skillable Workshop Instructions/Images/agents-aoai-select.jpeg)

2. 系統會為你創建一個新的 Agent。在 **Deployments** 部分，確保選擇 **gpt-4o-mini** 模型。

    > [!TIP]  
    > **確保選擇正確的部署**。應顯示 **gpt-4o-mini** 及其版本。

3. 接下來，為 Agent 命名。在 Agent Name 文本框中輸入以下內容：

    ```Contoso Outdoor Sales Agent```

4. 接下來，我們可以為 Agent 提供 **指令**。類似於我們在前面部分看到的 *System Message*，它為 Agent 提供需要遵循的目標。導航到 **Prompt** 標籤頁，並將以下指令複製到指令文本框中。

    ``` 
    You are a sales Agent for Contoso Outdoor. You are polite, professional, helpful and friendly.

    You get all the sales data from the uploaded .csv files. There is sales revenue data that is broken down by region, product category, product type and separated by year and month.

    Examples of regions include Africa, Asia, Europe and America. Categories include climbing gear, camping equipment, apparel and others. Product categories include jackets, hammocks, wet suits, shoes and more. 

    If a question is not related to sales or you cannot answer the question, you **must** respond: "Please contact IT for more assistance". If the user asks for help or says 'help', provide a list of sample questions that you can answer.
    ```

    ![Agents Playground 截圖](../../../../lab/Skillable Workshop Instructions/Images/agents-playground-update-details.jpeg)

    > [!NOTE]  
    > 你能在這段指令中辨識出多少來自前面部分的提示工程技術？提示請參考工作坊的第二部分。

5. 導航到 **Actions** 標籤頁，然後點擊 **add**。

    ![Agent 添加新文件的截圖](../../../../lab/Skillable Workshop Instructions/Images/agents-actions.jpeg)

6. 在新打開的標籤頁中，選擇 **Code interpreter**。

7. 在下一個窗口中，點擊 **select local files** 並選擇 `Contoso_Sales_Revenue.csv` file on your Desktop.
    ![Agents code interpreter](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-codeinterpreter-upload-file.jpeg)

    >[!NOTE]
    > If you cannot find the file on your desktop, you can download it from [here](../../../../lab/Skillable Workshop Instructions/assets/Contoso_Sales_Revenue.csv).

7. Click on the **upload and add** button. You should now see the file under the *Code Interpreter* tool.

The Agent is now ready for us to interact with it.

## Interacting with our Agent

1. On the top right of our Agents window, select **Try in playground**

![](../../../../lab/Skillable Workshop Instructions/Images/agents-try-in-playground.jpeg)

2.  Let's begin by typing `help` 文件。你會注意到這將啟動一個新的 Thread。  
你會看到一系列可以測試的範例問題。嘗試其中一個問題，看看 Agent 的回應！

8. 接下來，我們嘗試一個具體的查詢。輸入以下內容：

    ```What are the total sales for Europe broken down by category? ```

    你會注意到 Agent 使用代碼解釋器來為你提供答案。

9. 現在，讓我們嘗試處理這些數據。輸入以下提示：

    ```Put this data in a graph. ```

    通過代碼解釋器，Agent 能夠將結構化數據轉換成圖表！

10. 如果你想查看另一種類型的圖表，嘗試以下提示，並請求將數據以圖表形式呈現：

    ```What is the trending product category? Give the output as a graph. ```

    Agent 應該通過分析銷售收入數據的時間趨勢，為你提供展示熱門產品趨勢的圖表。

恭喜你！你現在已完成工作坊的最後部分，並學會了什麼是 Azure OpenAI Agents，它們如何運作，以及如何通過 Azure AI Foundry 入口創建它們。

點擊 **Next** 進入工作坊的總結部分。

**免責聲明**：  
本文件使用機器翻譯人工智慧服務進行翻譯。雖然我們努力確保準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。原始語言的文件應被視為具有權威性的來源。對於關鍵資訊，建議尋求專業人工翻譯。我們對於使用此翻譯所引起的任何誤解或誤讀概不負責。