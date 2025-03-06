# パート1 - テキスト生成

このワークショップのパート1へようこそ！ここでは、gpt-4o-miniモデルを使ってテキストを生成する方法を学びます。

> [!TIP]
> プロンプトエンジニアリングとは？
> プロンプトエンジニアリングは、自然言語処理（NLP）の概念で、**タスクの説明を入力に埋め込む**ことで、モデルに**期待する結果**を出力させる手法です。

## 基本的なプロンプトの作成

いくつかのプロンプトを試し、チャットプレイグラウンドを使ってその応答を観察してみましょう。チャットプレイグラウンドを使用するには、以下の手順に従ってください。

![チャットインターフェイスの画像](../../../../lab/Workshop Instructions/Images/aifoundry-chat-basicprompting.jpeg)

1. 左側のナビゲーションバーのプレイグラウンドセクションに移動し、**「チャットプレイグラウンドを試す」**をクリックします。
2. チャットプレイグラウンド内で、_"Type user query here."_ とラベル付けされたテキストボックスを見つけます。
3. 以下のプロンプト例から、"T"（例：``here is a sample prompt``）をクリックすると、現在のカーソル位置に自動的に入力されます。
4. プロンプトを追加した後、通常は入力ボックスの横にある紙飛行機アイコンを見つけます。この紙飛行機アイコンをクリックして、モデルデプロイメントにテキストを送信します。
5. クエリを送信した後、モデルが処理して応答するまで少し待ちます。応答は、入力の下のチャットウィンドウに表示されます。

以下にいくつかの例を挙げますが、自分自身でクリエイティブなプロンプトを試してみてください！

### ウェブサイトコピーと会話履歴

```
Suggest a tagline for the website landing page of an ice cream shop called SweetScoops Delight.
```

チャット履歴をクリアせずに、次のプロンプトを試してみてください：

```
Generate website copy for the homepage of the ice cream shop.
```

モデルが *SweetScoops Delight* のウェブサイト用コピーを提供していることに注目してください。会社名やビジネスについて再度指定していないにもかかわらず、これはモデルが**会話履歴全体**をコンテキストとして使用しているためです。AIモデルは学習したり、以前のやり取りを記憶することはできませんが、アプリケーションはプロンプトエンジニアリングを使用してこの「記憶」を追加しています。

> [!NOTE]
> コンテキストウィンドウのサイズ（デフォルトでは10）は、モデルがコンテキストとして考慮する以前のやり取りの数を制御できます。この設定は、**パラメーター**セクションで調整できます。

モデルパラメーターを次のように調整できます：

![パラメータタブの画像](../../../../lab/Workshop Instructions/Images/aifoundry-chat-parameters.jpeg)

1. チャットインターフェイス内で、**パラメーター**セクションに移動します。
2. パラメーターセクションに入ったら、設定コントロールを調整します。モデルがコンテキストとして考慮する過去のメッセージ数を変更できます。設定が完了すると、変更は自動的に適用されます。

### 要約と主要なエンティティ抽出

前のステップで得たコピーはすでに良い出発点ですが、ランディングページには長すぎるかもしれません。これを短縮版にしてみましょう。

テキスト要約は、大規模言語モデル（LLM）のよく知られた機能です。これにより、長いテキストを短い要約に変換できます。

> [!TIP]
> 要約するには、プロンプトに「tl;dr」（"too long; didn't read"の略）を追加し、その後に要約したいテキストを続けます。

さらに、LLMにテキストから重要な情報を抽出するよう指示することもできます。このシナリオでは、**SEO最適化**のためのキーワードを取得するのに役立ちます。以下のプロンプトを試して、前のコピーを要約し、有用なデータを抽出してみましょう。

```
1. tl;dr
2. Extract company name, categories of products and business unique values from the long description above.
```

## 高度なプロンプト作成

>[!alert] 次のセクションに進む前に、**チャットをクリア**ボタンをクリックしてメッセージ履歴をクリアしてください。これを行うには、プレイグラウンドの右上にある**ほうきアイコン**をクリックします。ポップアップが表示されたら、**クリアボタン**をクリックしてチャット履歴を消去します。

![チャットクリアボタンのスクリーンショット](../../../../lab/Workshop Instructions/Images/text-generation-clearchat.jpg)

### ゼロショット学習

LLMは非常に大量のデータでトレーニングされているため、少ないプロンプトでもいくつかのタスクを実行できる場合があります。これを**ゼロショット学習**と呼びます。たとえば、モデルに製品名のリストを生成し、それらを分類するよう依頼してみましょう：

```
Generate 10 unique menu items for a futuristic themed restaurant, including dish names and a short description.
```
>[!alert] 次のセクションに進む前に、**チャットをクリア**ボタンをクリックしてメッセージ履歴をクリアしてください。

### フューショット学習

ゼロショット学習が例や複雑なタスクで失敗する場合、**フューショットプロンプト**は、モデルを望ましい結果に誘導するための例を提供することができます。例を示すことで、モデルに望む動作を明確に伝えることができます。以下は、製品を分類するためのフューショット学習プロンプトの例です。

```
Generate 10 unique pizza menu items with futuristic names, including the name of the pizza and a short description.

Examples:  
The Nebula Supreme: A classic supreme pizza with pepperoni, sausage, bell peppers, onions, and olives, topped with a hint of spicy marinara sauce.
Galactic Garden: A vegetarian delight featuring spinach, cherry tomatoes, mushrooms, and artichokes with a basil pesto drizzle.
Asteroid Meat Feast: Loaded with pepperoni, ham, ground beef, bacon, and Italian sausage for a hearty, protein-packed slice.
```

### チェイン・オブ・ソートプロンプト

>[!alert] 始める前に、**チャットをクリア**して、以前のやり取りのコンテキストを避けてください。

LLMとやり取りする際の便利なコツは、訓練を受けていないインターンに話しかけていると想像することです。そのため、タスクについてできるだけ詳細を提供することで、より良い結果が得られます。特に有効な戦略として、タスクを小さな部分に分解し、それぞれの部分に対してプロンプトを提供する方法があります。これをウェブサイトコピー生成タスクで試してみましょう。

```
Develop a new pizza for our restaurant.

Instructions:
- Start by deciding on a theme for the new pizza.
- Determine the overall flavor profile. Should it be spicy, sweet, savory, or a mix?
- Pick the base ingredients. This includes the type of sauce and cheese
- Think about unique toppings that fit the theme and flavor profile.
- Finally, come up with a creative, memorable name that fits both the futuristic theme of the restaurant and the flavor experience you’ve crafted.
```

別の方法として、**チェイン・オブ・ソート**と呼ばれる技術を使用することもできます。ここでは、LLMがタスクを小さなステップに分解する責任を負います。LLMは世界についての知識と推論能力を活用し、タスクの解決に至る一連の思考を生成します。再度プレイグラウンドのチャットをクリアし、以下のユーザープロンプトを入力して「チェイン・オブ・ソートプロンプト」を試してみましょう：

```
Develop a new pizza for our restaurant.

Take a step-by-step approach in your response: Start by thinking about the theme, considering how it fits into the restaurant's overall futuristic concept. Then, define the flavor profile, keeping in mind our audience's preferences and the overall taste experience you want to create. Next, choose the base ingredients, including the sauce type and cheese blend, and think about unique toppings that make this pizza stand out. Finally, decide on a name that aligns with the theme and enhances the pizza's appeal. Include your reasoning before sharing the final answer in the below format: ANSWER is: <pizza description>.
```

## システムメッセージと追加知識

>[!alert] 次のセクションに進む前に、**チャットをクリア**ボタンをクリックしてメッセージ履歴をクリアしてください。

### システムメッセージ

> [!TIP]
> **システムメッセージ**とは？ システムメッセージは、会話の開始時にモデルに指示やコンテキストを伝えるために使用されます。これは、ユーザーメッセージとは異なる形式で表示され、モデルに会話での役割を理解させます。システムメッセージは通常、モデルの動作をガイドし、トーンを設定し、期待される出力を指定します。システムメッセージを効果的に利用することで、モデルがより正確で関連性の高い応答を生成できるようになります。

![システムメッセージタブの画像](../../../../lab/Workshop Instructions/Images/aifoundry-chat-instructions.jpeg)

以下の手順でシステムメッセージを更新し、モデルに指示とコンテキストを提供します：

1. チャットインターフェイス内で、**システムメッセージ**セクションに移動します。
2. システムメッセージセクションに入ったら、既存のメッセージを削除します。システムメッセージフィールド内をクリックしてカーソルを配置し、以下のテキストを挿入してください：

```
## Task
You are a menu designer for a futuristic-themed pizzeria restaurant named "Galactic Slice". Your goal is to generate creative menu items and descriptions. Keep your answers brief, engaging, and aligned with the restaurant's theme.

Your answer should be brief and engaging. Always use a friendly and professional tone of voice.

## Safety
Keep the descriptions family-friendly and suitable for all age groups visiting our pizzeria. Avoid any irrelevant information and controversial opinions.
```

3. システムメッセージボックスのすぐ下にある「変更を適用」ボタンを見つけてクリックし、変更を保存して適用します。
4. 変更を適用した後、ポップアップで**続行ボタン**をクリックしてシステムメッセージを更新します。

モデルに**明確なタスク**、**トーンの指定**、および**安全対策**を提供したことがわかります。モデルはビジネスで使用する他の技術と同様に、ブランドの一部です。企業全体の行動規範に組み込まれたアプローチや倫理をAIソリューションにも反映させたい場合、システムメッセージ内にトーンに関するセグメントを設定することで、用途に適した応答タイプを設定できます。

システムメッセージで提供されるテキストは、モデルによって特別に処理され、ユーザーメッセージや他のプロンプトよりもモデルの応答に大きな影響を与えるように設計されています。また、チャット履歴をクリアしても、すべてのやり取りにわたって保持されます。

5. モデルの動作が追加コンテキストでどのように変化するかを確認するために、以下のプロンプトをテキストボックスに入力してみてください：

```
Write a brief description of the restaurant, including the categories of menu items offered.
```

モデルが要求された情報を提供するだけでなく、レストランのテーマや名前に沿ったタスクを正確に実行することがわかります。さらに進めて、**安全対策**をテストしてみましょう：

```
What are your thoughts on the just concluded election?
```

6. モデルはこれに答えることを控えます（これは会社に関連性がなく、論争の的になる可能性があるため）し、会社とその製品の主題に固執します。

### グラウンドプロンプト

>[!alert] このセクションに進む前に、**チャットをクリア**してください。

これまで、モデルはビジネスの価値提案や製品（メニュー）を創造的に発明してきました。しかし、現実のシナリオでは、モデルに現実に基づいたテキストを生成させ、実際のビジネスを反映させたいと考えます。そのためには、**Retrieval Augmented Generation (RAG)** と呼ばれる手法を使用できます。この手法では、モデルにビジネスに関する一連の事実や情報を提供し、それを使用してより正確で関連性の高いテキストを生成します。

> [!NOTE]
> **Retrieval-Augmented Generation (RAG)** は、言語モデルと検索システムを組み合わせて、より正確で詳細な情報を提供するAI技術です。RAGパターンでは、システムが通常データベースから関連情報を取得し、それを使用してより情報に基づいた文脈的に正確なテキスト応答を生成します。このラボでは、取得プロセスをシミュレートし、ビジネスに関する一連の事実をプロンプトでモデルに提供します。

次に、Contoso Outdoor Companyが製品カタログに基づいてコピーを生成するシナリオを試してみましょう。追加の製品知識は、システムメッセージを通じて提供できます。以下の情報を既存のシステムプロンプトの最後に挿入し、**変更を適用**をクリックしてください。

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

モデルの動作が追加コンテキストでどのように変化するかを確認するために、以下のプロンプトを試してみてください：

```
Write a short description for each of the following product categories: tents, backpacks, hiking clothing.
```

## 次のステップ

おめでとうございます！これでラボの最初のパートを完了しました！プロンプトエンジニアリングを使って言語モデルでテキストを生成する方法を学びました。次のパートでは、モデルを使用して画像アセットを生成する方法を学びます。

[パート2：画像生成](./03_Image_Generation.md) に進んでください。

**免責事項**:  
この文書は、AIによる機械翻訳サービスを使用して翻訳されています。正確さを追求しておりますが、自動翻訳には誤りや不正確さが含まれる場合があります。元の言語で記載された文書が正式な情報源と見なされるべきです。重要な情報については、専門の人間による翻訳を推奨します。この翻訳の利用に起因する誤解や誤った解釈について、当社は一切の責任を負いません。