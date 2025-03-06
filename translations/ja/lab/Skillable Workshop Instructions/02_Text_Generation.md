# パート1 - テキスト生成

このワークショップのパート1へようこそ。ここでは、gpt-4o-miniモデルと対話しながらテキストを生成します。

> [!TIP]
> プロンプトエンジニアリングとは？
> プロンプトエンジニアリングは、自然言語処理 (NLP) の概念で、タスクの説明を入力に埋め込むことで、モデルに**期待する結果**を出力させる手法です。

## 基本的なプロンプト

いくつかのプロンプトを試し、チャットプレイグラウンドを使ってその応答を観察してみましょう。チャットプレイグラウンドを使用するには、以下の手順に従ってください。

![チャットインターフェースを示す画像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-basicprompting.jpeg)

1. 左側のナビゲーションバーでプレイグラウンドセクションに移動し、**Try the Chat Playground** をクリックします。
2. チャットプレイグラウンドで、_"Type user query here."_ とラベル付けされたテキストボックスを見つけます。
3. 以下のプロンプト例から "T"（例：``here is a sample prompt``）をクリックすると、現在のカーソル位置に自動的に入力されます。
4. プロンプトを追加したら、通常入力ボックスの横にある紙飛行機アイコンを見つけます。このアイコンをクリックして、モデルにテキストを送信します。
5. クエリを送信した後、モデルが処理して応答するまで少し待ちます。応答は、入力の下にあるチャットウィンドウに表示されます。

以下は試してみる例ですが、独自のプロンプトを作って試してみるのも面白いでしょう！

### ウェブサイトコピーと会話履歴

```
Suggest a tagline for the website landing page of an ice cream shop called SweetScoops Delight.
```

チャット履歴をクリアせずに、次のプロンプトを試してください：

```
Generate website copy for the homepage of the ice cream shop.
```

モデルが *SweetScoops Delight* のウェブサイト用コピーを提供していることに注目してください。会社名や事業内容を再度指定しなくても、このような結果が得られるのは、モデルが最新のプロンプトだけでなく、**会話全体の履歴**を文脈として考慮しているためです。AIモデルは学習や記憶を持ちませんが、アプリケーションがプロンプトエンジニアリングを活用してこの「記憶」を追加しています。

> [!NOTE]
> モデルが文脈として考慮する過去のやり取りの数（デフォルトは10）は、**Parameters** セクションで調整できます。

モデルのパラメータを次のように制御できます：

![パラメータタブを示す画像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-parameters.jpeg)

1. チャットインターフェースで、**Parameters** セクションに移動します。
2. Parameters セクションで設定を調整します。モデルが文脈として考慮する過去のメッセージの数を変更できます。設定が完了すると、自動的に適用されます。

### 要約と主要情報の抽出

前のステップで得られたコピーは、良い出発点ですが、ランディングページには少し長すぎるかもしれません。これを短くしてみましょう。

テキスト要約は、大規模言語モデル (LLM) のよく知られた機能で、大きなテキストを短く要約します。

> [!TIP]
> 要約するには、プロンプトに "tl;dr"（"too long; didn't read" の略）を追加し、その後に要約したいテキストを入力します。

さらに、LLM にテキストから重要な情報を抽出するよう指示することもできます。この機能は、**SEO最適化**のためのキーワード取得に役立ちます。次のプロンプトを試して、前のコピーを要約し、有用なデータを抽出してみましょう。

```
1. tl;dr
2. Extract company name, categories of products and business unique values from the long description above.
```

## 高度なプロンプト

>[!alert] 次のセクションに進む前に、**Clear Chat** ボタンをクリックしてメッセージ履歴をクリアしてください。これを行うには、プレイグラウンドの右上にある**ほうきのようなアイコン**をクリックします。ポップアップが表示されたら、**clear button** をクリックして履歴をクリアします。

![チャットクリアボタンのスクリーンショット](../../../../lab/Skillable Workshop Instructions/Images/text-generation-clearchat.jpg)

### Zero-shot learning

LLMは非常に大量のデータで訓練されているため、わずかなプロンプトでタスクを実行できることがあります。これを**ゼロショット学習**といいます。たとえば、製品名のリストを生成し、それをカテゴリ分けするようモデルに依頼してみましょう：

```
Generate 10 unique menu items for a futuristic themed restaurant, including dish names and a short description.
```
>[!alert] 次のセクションに進む前に、**Clear Chat** ボタンをクリックしてメッセージ履歴をクリアしてください。

### Few-shot learning

ゼロショット学習がうまくいかない場合や、より複雑なタスクの場合、**Few-shotプロンプト**を使用して例を提供すると、モデルをより目的に近づけることができます。例は、モデルにどのように動作してほしいかを明確に示します。以下は、製品をカテゴリ分けするためのFew-shotプロンプトの例です。

```
Generate 10 unique pizza menu items with futuristic names, including the name of the pizza and a short description.

Examples:  
The Nebula Supreme: A classic supreme pizza with pepperoni, sausage, bell peppers, onions, and olives, topped with a hint of spicy marinara sauce.
Galactic Garden: A vegetarian delight featuring spinach, cherry tomatoes, mushrooms, and artichokes with a basil pesto drizzle.
Asteroid Meat Feast: Loaded with pepperoni, ham, ground beef, bacon, and Italian sausage for a hearty, protein-packed slice.
```

### Chain of thought prompting

>[!alert] 始める前に、**Clear Chat** をクリックして、以前のやり取りの文脈をクリアしてください。

LLMと対話する際の便利なコツは、未熟なインターンに話しかけていると想像することです。タスクについて詳細を提供すればするほど、より良い結果が得られます。特に有用な戦略として、タスクを小さな部分に分解し、それぞれの部分にプロンプトを提供する方法があります。ウェブサイトコピー生成タスクでこれを試してみましょう。

```
Develop a new pizza for our restaurant.

Instructions:
- Start by deciding on a theme for the new pizza.
- Determine the overall flavor profile. Should it be spicy, sweet, savory, or a mix?
- Pick the base ingredients. This includes the type of sauce and cheese
- Think about unique toppings that fit the theme and flavor profile.
- Finally, come up with a creative, memorable name that fits both the futuristic theme of the restaurant and the flavor experience you’ve crafted.
```

もう一つの方法として、**Chain of thought** と呼ばれるテクニックがあります。この方法では、LLMがタスクを小さなステップに分解する責任を負います。LLMはその知識と推論能力を活用し、タスクの解決に至る一連の思考を生成します。再びチャット履歴をクリアしてから、以下のユーザープロンプトを入力し、"Chain of thought prompting" を実践してみましょう：

```
Develop a new pizza for our restaurant.

Take a step-by-step approach in your response: Start by thinking about the theme, considering how it fits into the restaurant's overall futuristic concept. Then, define the flavor profile, keeping in mind our audience's preferences and the overall taste experience you want to create. Next, choose the base ingredients, including the sauce type and cheese blend, and think about unique toppings that make this pizza stand out. Finally, decide on a name that aligns with the theme and enhances the pizza's appeal. Include your reasoning before sharing the final answer in the below format: ANSWER is: <pizza description>.
```

## システムメッセージと追加知識

>[!alert] 次のセクションに進む前に、**Clear Chat** ボタンをクリックしてメッセージ履歴をクリアしてください。

### システムメッセージ

> [!TIP]
> **システムメッセージ**とは？
> システムメッセージは、会話の冒頭でモデルに指示や文脈を伝えるために使用されます。これはユーザーメッセージとは異なる形式で表示され、モデルに会話での役割を理解させます。システムメッセージは通常、モデルの挙動を導き、トーンを設定し、望ましい出力を指定するために使用されます。システムメッセージを効果的に活用することで、より正確で関連性の高い応答を生成するようモデルを誘導できます。

![システムメッセージタブを示す画像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-instructions.jpeg)

システムメッセージを以下のように更新して、モデルに指示と文脈を与えます：

1. チャットインターフェースで、**System message** セクションに移動します。
2. System message セクションで既存のメッセージを削除します。System message フィールド内をクリックしてカーソルを配置し、以下のテキストを挿入してください：

```
## Task
You are a menu designer for a futuristic-themed pizzeria restaurant named "Galactic Slice". Your goal is to generate creative menu items and descriptions. Keep your answers brief, engaging, and aligned with the restaurant's theme.

Your answer should be brief and engaging. Always use a friendly and professional tone of voice.

## Safety
Keep the descriptions family-friendly and suitable for all age groups visiting our pizzeria. Avoid any irrelevant information and controversial opinions.
```

3. System message ボックスの直下にある **Apply changes** ボタンを見つけます。このボタンをクリックして、System message フィールドに加えた変更を保存し、適用します。
4. 変更を適用した後、ポップアップ内の **continue button** をクリックしてシステムメッセージを更新します。

モデルに**明確なタスク**、**トーン**、**安全対策**を指示したことがわかります。ビジネスに使用するテクノロジーとして、モデルもブランドの一部です。ビジネス全体で行動規範に組み込んでいるアプローチや倫理観をモデルにも反映させたい場合、システムメッセージにトーンを設定するセグメントを追加することで、ユースケースに適した応答タイプを設定できます。

システムメッセージで提供されたテキストは、モデルによって特別に処理され、ユーザーメッセージや他のプロンプトで提供される文脈よりも強い影響を与えることを意図しています。また、チャット履歴をクリアしても、このシステムメッセージはすべてのやり取りにわたって持続します。

5. 追加された文脈でモデルの挙動がどのように変わるかを確認するために、以下のプロンプトをテキストボックスに入力してみてください：

```
Write a brief description of the restaurant, including the categories of menu items offered.
```

モデルが要求された情報を提供するだけでなく、レストランのテーマや名前に忠実であることがわかります。さらに進めて、**安全対策**をテストすることもできます：

```
What are your thoughts on the just concluded election?
```

6. モデルはこれに回答を控えます（これは会社に無関係であり、論争を引き起こす可能性があるため）し、会社やその製品に関連する話題に留まります。

### 現実に基づいたプロンプト

>[!alert] このセクションに進む前に、必ず**Clear Chat**を実行してください。

これまで、モデルはビジネスの価値提案や製品（メニュー）を創造的に発明してきました。しかし、現実のシナリオでは、モデルに現実に基づいたテキストを生成させ、実際のビジネスを反映させたい場合があります。これを達成するために、**Retrieval Augmented Generation (RAG)** と呼ばれる手法を使用できます。この手法では、モデルにビジネスに関する事実や情報を提供し、それを基にしてより正確で関連性の高いテキストを生成します。

> [!NOTE]
> **Retrieval-Augmented Generation (RAG)** は、言語モデルと検索システムを組み合わせて、より正確で詳細な情報を提供するAI技術です。RAGパターンでは、通常、データベースから関連情報を取得し、それを使用してより情報に基づいた文脈的に正確なテキスト応答を生成します。このラボでは、モデルにビジネスに関する事実をプロンプトとして提供することで、検索プロセスをシミュレートします。

次に、Contoso Outdoor Companyが製品カタログに基づいてコピーを生成するシナリオに切り替えてみましょう。製品情報はシステムメッセージを通じて提供できます。以下の情報を既存のシステムプロンプトの最後に挿入し、**Apply changes** をクリックしてください。

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

追加された文脈でモデルの挙動がどのように変わるかを確認するために、以下のプロンプトを試してください：

```
Write a short description for each of the following product categories: tents, backpacks, hiking clothing.
```

## 次のステップ

おめでとうございます！ラボの最初のパートを完了しました。プロンプトエンジニアリングを使用して言語モデルを活用し、テキストを生成する方法を学びました。次のパートでは、モデルを使用して画像アセットを生成する方法を学びます。

**Next** をクリックして、画像セクションに進んでください。

**免責事項**:  
本書類は、機械翻訳AIサービスを使用して翻訳されています。正確性を期すよう努めておりますが、自動翻訳にはエラーや不正確な部分が含まれる可能性があります。原文（元の言語で書かれた文書）が正式な情報源とみなされるべきです。重要な情報については、専門の人間による翻訳をお勧めします。本翻訳の使用により生じた誤解や誤解釈について、当方は一切の責任を負いません。