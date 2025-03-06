# Part 4 - Azure AI エージェント

このワークショップの第4部へようこそ！

これまでに、さまざまな方法で大規模言語モデルとやり取りしてきました。ただし、これらのやり取りはそれぞれ独立しており、非常に特定の目的に結び付いていました。**Azure AI エージェント**は、これらのやり取りを統合して一つのソリューションにすることで、次のステップを提供します。

> [!TIP] 
> **Azure AI エージェントとは？**  
> Azure AI エージェントは、開発者が基盤となるコンピューティングやストレージリソースを管理する必要なく、安全に高品質で拡張性のあるAIエージェントを構築、展開、スケールできるように設計された完全マネージドサービスです。状態管理、コンテキストの関連付け、チャットスレッド、コード実行などの機能を統合しており、サードパーティの拡張機能に簡単にアクセスできるようにします。

以前は、カスタムAIエージェントを構築するには、経験豊富な開発者であっても多大な労力が必要でした。チャット補完APIは軽量で強力ですが、本質的にステートレスであるため、開発者は会話の状態やチャットスレッド、ツールの統合、ドキュメントやインデックスの取得、コードの実行を手動で管理する必要がありました。

Azure AI Foundry内では、AIエージェントは「スマート」なマイクロサービスとして機能し、質問に答えたり（RAG）、アクションを実行したり、ワークフローを完全に自動化したりできます。これを実現するために、生成AIモデルの力と、現実世界のデータソースにアクセスしてやり取りできるツールを組み合わせています。

エージェントは必要に応じて複数のツールに並行してアクセスすることもできます。これらのツールには以下が含まれます：
- **Function Calling**
- **Code Interpreter**
- **File Search**
- **Bing 検索によるグラウンディング**
- **Azure Functions** など

このセクションでは、Code Interpreterについて説明します。

## エージェントの構成要素を理解する

Azure AI エージェントを使用し始めるには、その機能に関与するさまざまな構成要素を理解しておくことが重要です。

すでに学んだように、**エージェント**とは、RAGを使用して質問に答えたり、アクションを実行したり、ワークフローを自動化したりする「スマート」なマイクロサービスのことです。

エージェントが作成された後の次のステップは、**スレッド**を作成することです。**スレッド**とは、エージェントとユーザー間の会話セッションを指します。スレッドはメッセージを保存し、モデルのコンテキストに収まるように内容を自動的に切り詰めます。

**メッセージ**はエージェントまたはユーザーによって作成され、テキスト、画像、その他のファイルを含みます。これらはスレッド内のリストとして保存されます。

最後に、エージェントを**実行**することができます。これは、スレッドの内容に基づいてエージェントをアクティブにすることを意味します。エージェントはその構成と*スレッドのメッセージ*を使用して、モデルやツールを呼び出してタスクを実行します。実行の一環として、エージェントは*スレッドにメッセージを追加*します。

## エージェントの作成

1. 左側のナビゲーションバーで、_Build and customize_ の下にある **Agents** を選択します。新しく開いたページで、下矢印をクリックしてAzure OpenAI Serviceリソースを選択し、**Let's go** ボタンを選択します。

![Azure OpenAI Service Resourceを選択するスクリーンショット](../../../../lab/Workshop Instructions/Images/agents-aoai-select.jpeg)

2. 新しいエージェントがすでに作成されています。**Deployments** セクションで、**gpt-4o-mini** モデルを選択していることを確認してください。

    >[!TIP] 
    > **正しいデプロイメントを選択してください**。**gpt-4o-mini** とそのバージョンが表示されているはずです。

3. 次に、エージェントに名前を付けます。エージェント名のテキストボックスに以下を入力してください：

    ```Contoso Outdoor Sales Agent```

4. 次に、エージェントに**指示**を与えることができます。前のセクションで見た*System Message*と同様に、エージェントに従うべき目標を提供します。**Prompt** タブに移動し、以下の指示を指示テキストボックスにコピーしてください。

    ``` 
    You are a sales Agent for Contoso Outdoor. You are polite, professional, helpful and friendly.

    You get all the sales data from the uploaded .csv files. There is sales revenue data that is broken down by region, product category, product type and separated by year and month.

    Examples of regions include Africa, Asia, Europe and America. Categories include climbing gear, camping equipment, apparel and others. Product categories include jackets, hammocks, wet suits, shoes and more. 

    If a question is not related to sales or you cannot answer the question, you **must** respond: "Please contact IT for more assistance". If the user asks for help or says 'help', provide a list of sample questions that you can answer.
    ```

    ![Agents Playground](../../../../lab/Workshop Instructions/Images/agents-playground-update-details.jpeg)

    >[!NOTE]
    >このプロンプトの中に、以前のセクションで学んだプロンプトエンジニアリングのテクニックがいくつあるか確認してみましょう。ヒントはワークショップの第2部にあります。

5. **Actions** タブに移動し、**add** をクリックします。

    ![エージェントに新しいファイルを添付する](../../../../lab/Workshop Instructions/Images/agents-actions.jpeg)

6. 新しいタブが開きます。そこで **Code interpreter** を選択します。

7. 次のウィンドウで、**select local files** をクリックし、`Contoso_Sales_Revenue.csv` file on your Desktop.
    ![Agents code interpreter](../../../../lab/Workshop Instructions/Images/aifoundry-codeinterpreter-upload-file.jpeg)

    >[!NOTE]
    > If you cannot find the file on your desktop, you can download it from [here](../../../../lab/Workshop Instructions/assets/Contoso_Sales_Revenue.csv).

7. Click on the **upload and add** button. You should now see the file under the *Code Interpreter* tool.

The Agent is now ready for us to interact with it.

## Interacting with our Agent

1. On the top right of our Agents window, select **Try in playground**

![](../../../../lab/Workshop Instructions/Images/agents-try-in-playground.jpeg)

2.  Let's begin by typing `help` を選択します。これにより、新しいスレッドが開始されます。  
チャットボックスにはテスト用のサンプル質問がいくつか表示されます。質問の一つを試してみて、エージェントの回答を確認してください！

8. 次に、特定のクエリを試してみましょう。以下を入力してください：

    ```What are the total sales for Europe broken down by category? ```

    エージェントがコードインタープリタを使用して回答を提供することに気付くでしょう。

9. さらに、このデータを操作してみましょう。以下のプロンプトを入力してください：

    ```Put this data in a graph. ```

    コードインタープリタを通じて、エージェントは構造化データをグラフに変換することができます！

10. 別の種類のグラフを見たい場合は、以下のプロンプトを試し、データをグラフにするようリクエストしてください：

    ```What is the trending product category? Give the output as a graph. ```

    エージェントは、売上収益データの時間経過に基づいてトレンド製品を示すグラフを提供するはずです。

おめでとうございます！これでワークショップの最後の部分を完了し、Azure OpenAI エージェントとは何か、それがどのように機能するか、そしてAzure AI Studioを使用してエージェントを作成する方法を学びました。

ワークショップの最終セクションへ進んでください：[Summary](./07_Summary.md)

**免責事項**:  
この文書は、機械ベースのAI翻訳サービスを使用して翻訳されています。正確性を期すよう努めていますが、自動翻訳には誤りや不正確さが含まれる可能性があります。元の言語で記載された原文が信頼できる情報源と見なされるべきです。重要な情報については、専門の人間による翻訳をお勧めします。本翻訳の利用によって生じる誤解や解釈の誤りについて、当社は一切責任を負いません。