# 第 1 部分 - 文本生成

歡迎來到這次工作坊的第 1 部分，我們將與 gpt-4o-mini 模型互動，生成文本內容。

> [!TIP]  
> 什麼是提示工程（prompt engineering）？  
> 提示工程是自然語言處理（NLP）中的一個概念，涉及將**任務的描述嵌入到輸入中**，以**引導模型**生成**期望的結果**。

## 基本提示

讓我們從一些簡單的提示開始，並在聊天操作台中觀察模型的回應。要使用聊天操作台，請按照以下步驟操作：

![展示聊天界面的圖片](../../../../lab/Workshop Instructions/Images/aifoundry-chat-basicprompting.jpeg)

1. 在左側導航欄中找到 **Playgrounds** 區域，然後點擊 **Try the Chat Playground**。
2. 在聊天操作台中，找到標有 _"Type user query here."_ 的文本框。
3. 從以下的提示範例中點擊 "T"（例如 ``here is a sample prompt``），這將自動將內容插入到當前光標位置，只需點擊一次即可。
4. 添加提示後，找到通常位於輸入框旁邊的紙飛機圖標。點擊紙飛機圖標以提交您的文本到模型部署。
5. 發送查詢後，稍等片刻讓模型處理並回應。回應將顯示在輸入框下方的聊天窗口中。

以下是一些範例，您也可以創造自己的提示來試試看會發生什麼！

### 網站文案與對話歷史

```
Suggest a tagline for the website landing page of an ice cream shop called SweetScoops Delight.
```

在不清除聊天歷史的情況下，試試以下提示：

```
Generate website copy for the homepage of the ice cream shop.
```

請注意，即使我們沒有再次指定公司名稱或業務，模型仍然生成了 *SweetScoops Delight* 網站的文案。這是因為模型在後台會將**整個對話歷史**作為上下文，而不僅僅是最新的提示。如果用戶離開後再回來，AI 模型無法學習或記住先前的互動，但應用程式使用提示工程來添加這種“記憶”。

> [!NOTE]  
> 您可以控制上下文窗口的大小，也就是模型考慮為上下文的先前互動次數（默認為 10），這可以在 **Parameters** 區域進行調整。

您可以按以下步驟控制模型參數：

![展示參數標籤的圖片](../../../../lab/Workshop Instructions/Images/aifoundry-chat-parameters.jpeg)

1. 在聊天界面中，導航到 **Parameters** 區域。
2. 進入參數區域後，調整設置控件。您可以更改模型考慮為上下文的過去消息數量。設置完成後，變更會自動生效。

### 摘要與關鍵實體提取

我們從前一步驟中獲得的文案已經是一個很好的起點，但它可能對於登陸頁面來說太長了。讓我們試著獲取它的簡短版本。

文本摘要是大型語言模型（LLMs）的一個知名功能，它能從較長的文本中生成簡短的摘要。

> [!TIP]  
> 要進行摘要，可以在提示中添加 "tl;dr"（意為 "too long; didn't read"），後面接著您想要摘要的文本。

此外，您還可以指示 LLM 從文本中提取關鍵信息。在我們的情境中，這對於獲取 **SEO 優化**的關鍵詞非常有用。試試以下提示來摘要之前的文案，然後提取有用的數據。

```
1. tl;dr
2. Extract company name, categories of products and business unique values from the long description above.
```

## 進階提示

>[!alert] 在進入下一部分之前，請點擊 **Clear Chat** 按鈕以清除消息歷史。要執行此操作，請點擊操作台右上角的**掃帚圖標**。彈出窗口出現後，點擊 **clear 按鈕** 清除聊天歷史。

![清除聊天按鈕的截圖](../../../../lab/Workshop Instructions/Images/text-generation-clearchat.jpg)

### 零樣本學習

LLMs 訓練於大量數據集上，因此它們可能能夠在極少的提示下完成某些任務。這被稱為 **零樣本學習**。例如，我們可以要求模型生成一份產品名稱清單並對其進行分類：

```
Generate 10 unique menu items for a futuristic themed restaurant, including dish names and a short description.
```  
>[!alert] 在進入下一部分之前，請點擊 **Clear Chat** 按鈕以清除消息歷史。

### 少樣本學習

如果零樣本學習無法滿足您的範例或更複雜的任務，**少樣本提示**可以提供一些範例來更好地引導模型達到期望的結果。範例清楚地向模型展示了我們希望它如何操作。以下是一個用於分類產品的少樣本學習提示範例。

```
Generate 10 unique pizza menu items with futuristic names, including the name of the pizza and a short description.

Examples:  
The Nebula Supreme: A classic supreme pizza with pepperoni, sausage, bell peppers, onions, and olives, topped with a hint of spicy marinara sauce.
Galactic Garden: A vegetarian delight featuring spinach, cherry tomatoes, mushrooms, and artichokes with a basil pesto drizzle.
Asteroid Meat Feast: Loaded with pepperoni, ham, ground beef, bacon, and Italian sausage for a hearty, protein-packed slice.
```

### 思維鏈提示

>[!alert] 開始之前，請點擊 **Clear Chat** 清除任何來自先前互動的上下文。

與 LLMs 互動時，一個有用的技巧是想像您正在與一位未受訓的實習生交談。因此，您提供的任務細節越多，結果就會越好。一種特別有用的策略是將任務分解為更小的部分，並為每個部分提供提示。讓我們用網站文案生成任務來試試看。

```
Develop a new pizza for our restaurant.

Instructions:
- Start by deciding on a theme for the new pizza.
- Determine the overall flavor profile. Should it be spicy, sweet, savory, or a mix?
- Pick the base ingredients. This includes the type of sauce and cheese
- Think about unique toppings that fit the theme and flavor profile.
- Finally, come up with a creative, memorable name that fits both the futuristic theme of the restaurant and the flavor experience you’ve crafted.
```

另一種選擇是使用一種技術，稱為 **思維鏈（chain of thought）**，讓 LLM 負責將任務分解為更小的步驟。LLM 使用其對世界的知識和推理能力，生成一條思維鏈，從而解決任務。再次清除操作台的聊天記錄，然後輸入以下用戶提示，看看“思維鏈提示”如何運作：

```
Develop a new pizza for our restaurant.

Take a step-by-step approach in your response: Start by thinking about the theme, considering how it fits into the restaurant's overall futuristic concept. Then, define the flavor profile, keeping in mind our audience's preferences and the overall taste experience you want to create. Next, choose the base ingredients, including the sauce type and cheese blend, and think about unique toppings that make this pizza stand out. Finally, decide on a name that aligns with the theme and enhances the pizza's appeal. Include your reasoning before sharing the final answer in the below format: ANSWER is: <pizza description>.
```

## 系統消息與附加知識

>[!alert] 在進入下一部分之前，請點擊 **Clear Chat** 按鈕以清除消息歷史。

### 系統消息

> [!TIP]  
> 什麼是 **系統消息（system message）**？  
> 系統消息用於在對話開始時向模型傳達指令或提供上下文。它以不同於用戶消息的格式顯示，幫助模型理解其在對話中的角色。系統消息通常用於指導模型的行為、設定語氣或指定期望的輸出。通過有效利用系統消息，用戶可以引導模型生成更準確且相關的回應。

![展示系統消息標籤的圖片](../../../../lab/Workshop Instructions/Images/aifoundry-chat-instructions.jpeg)

更新系統消息以提供如下的指令與上下文：

1. 在聊天界面中，導航到 **System message** 區域。
2. 進入系統消息區域後，刪除現有消息。點擊系統消息框內，將以下文本插入其中：

```
## Task
You are a menu designer for a futuristic-themed pizzeria restaurant named "Galactic Slice". Your goal is to generate creative menu items and descriptions. Keep your answers brief, engaging, and aligned with the restaurant's theme.

Your answer should be brief and engaging. Always use a friendly and professional tone of voice.

## Safety
Keep the descriptions family-friendly and suitable for all age groups visiting our pizzeria. Avoid any irrelevant information and controversial opinions.
```

3. 找到標有 Apply changes 的按鈕，它位於系統消息框的正下方。點擊此按鈕保存並應用您對系統消息字段所做的更改。
4. 應用更改後，點擊彈出窗口中的 **continue 按鈕** 更新系統消息。

請注意，我們為模型提供了**明確的任務**、**語氣指導**以及**安全措施**。您的模型就像業務中使用的任何技術一樣，是您品牌的一部分。如果您希望它具備與您企業行為準則一致的方法和倫理，也應在您的 AI 解決方案中包含這些要求。在系統消息中設置語氣相關的內容，可以幫助調整回應類型以適應您的使用場景。

系統消息中的文本被模型特別處理，通常對模型的回應有比用戶消息文本或提示中其他上下文更大的影響。而且，即使清除了聊天歷史，系統消息也會持續作用於所有互動。

5. 為了觀察模型的行為如何隨著上下文的增加而改變，請在文本框中試試以下提示：

```
Write a brief description of the restaurant, including the categories of menu items offered.
```

您會發現，模型不僅會提供請求的信息，還會準確執行任務，例如保持餐廳的主題和名稱一致。為了進一步測試，我們可以檢驗**安全措施**：

```
What are your thoughts on the just concluded election?
```

6. 模型將拒絕回答這類問題（因為它既與公司無關，又可能被視為具有爭議性），並將主題集中於公司及其產品。

### 基於事實的提示

>[!alert] 確保在進入本部分之前先 **Clear Chat**。

到目前為止，模型在創造業務價值主張和產品（菜單）方面非常有創意。然而，在真實世界的場景中，我們希望模型生成的文本能夠基於現實，並反映實際業務。為了實現這一點，我們可以使用一種稱為 **檢索增強生成（RAG）** 的技術。這種技術涉及向模型提供一組關於業務的事實或信息，模型可以利用這些信息生成更準確且相關的文本。

> [!NOTE]  
> **檢索增強生成（RAG）** 是一種結合語言模型與檢索系統的 AI 技術，用於提供更準確和詳細的信息。在 RAG 模式中，系統通常從數據庫中檢索相關信息，然後利用這些信息幫助生成更有依據且上下文準確的文本回應。為了完成本次實驗，我們將模擬檢索過程，通過提示向模型提供一組關於業務的事實。

讓我們切換到另一個場景，為 Contoso Outdoor Company 基於其產品目錄生成文案。附加的產品知識可以通過系統消息提供。在現有系統提示的末尾插入以下信息，然後點擊 **Apply changes**。

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

為了觀察模型的行為如何隨著上下文的增加而改變，請試試以下提示：

```
Write a short description for each of the following product categories: tents, backpacks, hiking clothing.
```

## 下一步

恭喜您完成了實驗的第一部分！您已經學會如何使用提示工程來生成語言模型的文本。在實驗的下一部分，您將學習如何使用模型生成圖像資產。

前往 [第 2 部分：圖像生成](./03_Image_Generation.md)

**免責聲明**：  
本文檔是使用基於機器的AI翻譯服務進行翻譯的。我們致力於提供準確的翻譯，但請注意，自動翻譯可能會包含錯誤或不準確之處。應以原始語言的文件作為權威來源。對於關鍵信息，建議尋求專業人工翻譯。我們對因使用本翻譯而引起的任何誤解或錯誤解釋不承擔責任。