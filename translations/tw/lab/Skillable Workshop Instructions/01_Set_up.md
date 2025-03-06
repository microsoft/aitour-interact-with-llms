# 開始使用

> [!TIP]
> 什麼是 **Azure AI Foundry**？Azure AI Foundry 是為創新者打造未來的終極平台。它提供一套完整的 Azure AI 功能和工具，用於設計、定制和管理 AI 應用和代理。它與全球最受歡迎的開發工具無縫集成，包括 GitHub、Visual Studio 和 Copilot Studio。Azure AI Foundry 讓開發者和 IT 管理員能輕鬆高效地實現他們的 AI 願景。

## 登錄 Windows
第一步，使用以下憑據登錄實驗室虛擬機：
- 使用者名稱：已設定為 Admin。
- 密碼：輸入 +++@lab.VirtualMachine(Win11Base23B-W11-22H2).Password+++ 並點擊。

> [!TIP]
> **第一次使用 Skillable？** 綠色的 "T"（例如，+++Admin+++）表示可以一鍵自動輸入到虛擬機當前游標位置的值。這樣可以減少你的操作並最小化輸入錯誤。

## 登錄 Azure AI Foundry 入口網站

在本次工作坊中，我們將使用 Azure AI Foundry 入口網站，特別是聚焦於 Playground 功能。

1. 在桌面上，點擊 **Microsoft Edge** 瀏覽器。導航到第二個瀏覽器標籤，該標籤將顯示 Azure AI Foundry 入口網站的主頁，如下圖所示。

![Azure AI Foundry 主頁](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-homepage.jpeg)

## 瀏覽 Azure AI Foundry 入口網站

1. 首先點擊 **Sign In**，你可以在窗口右上角找到登錄連結，並在提示登錄憑據時輸入以下資訊：
    - 電子郵件：+++@lab.CloudPortalCredential(User1).Username+++
    - 密碼：+++@lab.CloudPortalCredential(User1).Password+++

    現在我們已經登錄，可以開始探索這個平台。

2. 在可用的 Hub 列表中找到 **Workshop AI Hub**。**點擊該 Hub 的專案**以訪問其設定和資源。

![Hub 管理標籤](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-hub-navigation.jpeg)

## 專案

![專案概覽標籤](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-project-overview.jpeg)

### 專案概覽

在此頁面，我們可以看到 Azure AI Foundry 入口網站專案的概覽。包括：
- **專案名稱和描述**：專案的名稱和一段簡短描述。
- **專案詳細資訊**：包括專案的連接字串、位置、資源群組等屬性集合。
- **端點和金鑰**：Azure AI Foundry 入口網站支持連接多個資源，擴展其功能和特性。資源如 Azure OpenAI、Azure AI 搜索和 Azure AI 服務進一步增強了我們專案的能力，提供 LLM 部署或向量搜索等功能。在這裡可以找到 *API 端點和金鑰* 以及相關文檔。
- **最近的資源和教程**：在這裡，你的最近資源會被高亮顯示，並提供額外的學習資源和教程來幫助你快速入門。

### 導航欄

你會注意到導航欄已更新，新增了與我們專案相關的功能標籤。

![專案導航欄](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-project-navigation.jpeg)

我們有以下幾個新區域：
1. 第一部分包括 _Playgrounds_ 用於與模型互動，_Overview_ 提供專案的一般概覽，_Model Catalog_ 展示 Azure AI Foundry 中可用的模型，還有 _AI Services_，你可以在此查看可用的 Azure AI 服務及其演示、使用案例等。
2. **Build and Customize**：包括擴展專案範圍的機會，例如 _在代碼中工作_ 通過運行雲端計算，訪問 [_Prompt Flow_](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow)，以及對部署進行 _微調_。
3. **Assess and Improve**：包括為模型開發 _評估_，使用 _追踪_ 來調試流程，還有 _內容過濾器_ 用於對提示輸入和完成輸出添加安全防護。
4. **My assets**：在這裡你可以向專案添加額外的元素，例如 _數據_、_索引_、_模型和端點_ 以及 _Web 應用_。
5. **管理中心**：用於管理所有 Hub 和專案的詳細資訊與資源。

在這次實驗中，我們將專注於使用 **Playgrounds**，導航到 Playgrounds 並進入下一部分。

## Playgrounds

你會發現我們有不同的 **Playground** 選項。每個選項代表與 AI 模型交互和使用的不同方式，可以根據我們的具體需求進行定制。

我們將主要在這些 Playgrounds 中工作，特別是以下幾個：

1. **Chat Playground**
2. **Images Playground**
3. **Real-time audio playground**
4. **Agents playground**

![Azure AI Foundry Playgrounds 圖片](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-playgrounds.jpeg)

### Chat Playground

在 Playground 區域，導航到 **Chat playground** 並選擇 **Try the Chat Playground**。此功能允許你以對話形式與各種 AI 模型進行互動和測試。

![Azure AI Foundry Playground Chat 模式圖片](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-playground.jpeg)

1. **部署**：此區域允許我們在已部署的模型之間切換。
2. **系統訊息框**：在這裡輸入用於指導模型的指令，這些指令是在用戶交互之前設置的。
3. **添加你的數據**：Azure AI Foundry 入口網站支持為已部署的模型提供外部數據，從而改進搜索和上下文。
4. **參數**：此標籤包含模型的詳細設定，例如溫度參數。
5. **聊天框**：在這裡，我們可以看到與模型的互動記錄，以聊天訊息的形式呈現。
6. **提示框**：這是我們輸入要發送給模型的提示的地方。

### Images Playground

返回 Playgrounds，選擇 **Image playground** 並點擊 **Try the Image Playground**。此選項允許你進行圖像生成。

![Azure AI Foundry Playground Images 模式圖片](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-image-playground.jpeg)

1. **部署**：在這個下拉選單中，我們可以選擇用於圖像生成的模型。這些模型與聊天模型一樣，來自我們的部署。
2. **提示框**：類似於聊天 Playground 的提示框，這是模型從用戶那裡獲取輸入的地方。在圖像生成的情況下，輸入的是我們希望生成的圖像描述。
3. **結果框**：最後，這裡顯示生成的圖像。

### Real-time audio playground

返回 Playgrounds，然後選擇 **Real-time audio playground** 並點擊 **Try the Real-time audio Playground**。此功能允許你以音頻對話的形式與各種 AI 模型進行互動和測試。

![Azure AI Foundry Playground Real-time audio 模式圖片](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-real-time-audio.jpeg)

1. **部署**：此區域允許我們在已部署的模型之間切換。
2. **服務端回合檢測**：決定服務端是否應使用語音活動檢測（VAD）來識別用戶完成講話的時機。
3. **系統訊息框**：在這裡輸入用於指導模型的指令，這些指令是在用戶交互之前設置的。
4. **選擇語音**：gpt-4o-realtime 提供多種語音選項，具有不同的口音或音調能力，可以根據你的喜好進行選擇。
5. **服務端回合檢測**：額外參數，用於通過改進語音活動檢測來優化模型的效率和性能。
6. **參數**：此標籤包含模型的詳細設定，例如溫度和最大回應。
7. **提示按鈕**：類似於聊天 Playground 的提示框，這是模型從用戶那裡獲取輸入的地方。

## Agents playground

在導航欄中選擇 **Agents**。此功能提供工具來構建、測試和定制 AI 驅動的代理。

![Azure AI Foundry Playground Agents 模式圖片](../../../../lab/Skillable Workshop Instructions/Images/agents-playground-pt1.jpeg)

當你 _創建第一個代理_ 後，你將看到以下 UI 組件：
1. **代理 ID 和名稱**：在這裡你可以為代理命名。
2. **部署**：在這個下拉選單中，我們可以選擇用於圖像生成的模型。這些模型與聊天模型一樣，來自我們的部署。
3. **指令框**：在這裡輸入用於指導模型的指令，這些指令是在用戶交互之前設置的。

![](../../../../lab/Skillable Workshop Instructions/Images/agents-playground-pt2.jpeg)

4. **知識**：知識讓代理可以訪問數據來源，以增強回答的基礎。
5. **動作**：通過允許代理在運行時執行各種工具來提升其能力。
6. **模型設定**：此標籤包含模型的詳細設定，例如溫度和 Top P。
7. **提示框**：類似於聊天 Playground 的提示框，這是模型從用戶那裡獲取輸入的地方。

## 準備開始

以上涵蓋了 Azure AI Foundry 入口網站的必要設置和基礎知識。我們現在將繼續與模型進行互動。

- 導航到 **Playgrounds**，選擇 **Chat playground** 並點擊 **Try the Chat Playground**。
- 在 _指令標籤_ 中，點擊 Next 繼續到第一部分：文本生成。

點擊 **Next** 繼續到文本生成部分。

**免責聲明**：  
本文件是使用機器翻譯AI服務進行翻譯的。我們雖然努力確保準確性，但請注意，自動翻譯可能包含錯誤或不準確之處。應以原文檔的母語版本作為權威來源。對於關鍵信息，建議尋求專業人工翻譯。我們對於使用此翻譯所產生的任何誤解或誤讀概不負責。