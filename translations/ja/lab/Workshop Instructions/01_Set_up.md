# はじめに

> [!TIP]
> **Azure AI Foundry**とは？Azure AI Foundryは、未来を創造するための究極のプラットフォームです。Azure AIの包括的な機能とツールを提供し、AIアプリケーションやエージェントを設計、カスタマイズ、管理できます。GitHub、Visual Studio、Copilot Studioなど、世界中で愛されている開発者ツールとシームレスに統合されています。Azure AI Foundryは、開発者やIT管理者がAIのビジョンを簡単かつ効率的に実現することを可能にします。

## 前提条件

このラボを完了するには、以下が必要です：

- Azureサブスクリプション - [無料で作成できます。](https://azure.microsoft.com/free/cognitive-services?WT.mc_id=aiml-132569-bethanycheum)
- Azure OpenAIリソース（[サポートされている地域で利用可能なGPT-4oおよびDALL.E 3モデル](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models#assistants-preview?WT.mc_id=aiml-132569-bethanycheum)を含む）

## リソースのデプロイ

このワークショップでは、Azure AI Foundryを使用します。まず、以下の手順に従って必要なリソースをデプロイしてください：

1. Azureにリソースをデプロイするには、以下のボタンをクリックします：[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2Faitour-interact-with-llms%2Fmain%2Flab%2FWorkshop%20Instructions%2Fassets%2FAITour24_WKR540_Template.json)

2. 新しいタブで、Azureアカウントにサインインします。

3. サインイン後、カスタムテンプレートに基づいてリソースを作成するページにリダイレクトされます。新しいリソースグループを作成し、名前を**interact-with-llms**にします。

4. **Unique Suffix**フィールドに、任意のユニークな4文字を追加します。その後、**Review and Create**ボタンをクリックしてリソースを作成します。

> [!NOTE]
> リソースのデプロイには約2～3分かかります。

5. このワークショップでは、Azure AI Foundryの中でも特にプレイグラウンド機能に焦点を当てます。デプロイが完了したら、ブラウザで[Azure AI Foundry](https://ai.azure.com?WT.mc_id=aiml-132569-bethanycheum)にアクセスしてください。

## Azure AI Foundryのナビゲート

![Azure AI Foundry ログイン後のホームページ](../../../../lab/Workshop Instructions/Images/ai-Foundry-login-homepage.png)

1. まず、左サイドバーの**Management**セクションに移動します。このセクションの下にある**All Resources**を選択します。この操作で、利用可能なすべてのリソースとツールが表示される集中管理エリアに移動し、現在のハブ接続の概要を確認できます。

> [!NOTE]
> **All Resources**セクションが見つからない場合は、**All hubs**セクションをクリックしてください。

2. リストから**Workshop AI Hub**を見つけます。**ハブのプロジェクト**をクリックして、その設定とリソースにアクセスします。

![ハブ管理タブ](../../../../lab/Workshop Instructions/Images/aifoundry-hub-navigation.jpeg)

## プロジェクト

![プロジェクト概要タブ](../../../../lab/Workshop Instructions/Images/aifoundry-project-overview.jpeg)

### プロジェクト概要

このページでは、Azure AI Foundryポータルプロジェクトの概要を確認できます。以下が含まれます：
- **プロジェクト名と説明**: プロジェクト名とAzure AI Foundryポータルプロジェクトの簡単な説明。
- **プロジェクト詳細**: プロジェクトの接続文字列、場所、リソースグループなど、さまざまなプロパティのコレクション。
- **エンドポイントとキー**: Azure AI Foundryポータルでは、複数のリソースを接続でき、機能を拡張できます。Azure OpenAI、Azure AI Search、Azure AI Servicesなどのリソースは、LLMのデプロイやベクトル検索などの機能を提供します。ここでは、*APIエンドポイントとキー*やドキュメントなどの有用な情報を見つけることができます。
- **最近使用したリソースとチュートリアル**: 最近使用したリソースがハイライトされ、追加の学習リソースやチュートリアルが表示されます。

### ナビゲーションバー

ナビゲーションバーには、新しいタブが追加されており、プロジェクトに関連する機能が表示されています。

![プロジェクトナビゲーションバー](../../../../lab/Workshop Instructions/Images/aifoundry-project-navigation.jpeg)

新しいセクションは以下の通りです：
1. **Playgrounds**: モデルと対話するためのプレイグラウンド、プロジェクトの概要を提供する**Overview**、Azure AI Foundry内の利用可能なモデルを表示する**Model Catalog**、およびAzure AI Servicesをリスト化し、デモやユースケースなどを確認できる**AI Services**が含まれます。
2. **Build and Customize**: クラウドコンピュートでコードを実行する、[_Prompt Flow_](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow)にアクセスする、デプロイメントに対してファインチューニングを行うなど、プロジェクトの可能性を拡大する機能が含まれます。
3. **Assess and Improve**: モデルの評価を行う_Evaluations_、フローのデバッグを行う_tracing_、プロンプト入力や出力のガードレールを追加する_content filters_の開発が含まれます。
4. **My assets**: プロジェクトに追加要素を加えるためのセクションで、_Data_、_Indexes_、_models and endpoints_、_Web apps_などのリソースを使用できます。
5. **Management Center**: ハブとプロジェクトの詳細やリソースを管理するための場所。

このラボでは、主に**Playgrounds**を使用します。Playgroundsに移動し、次のセクションに進みます。

## Playgrounds

**Playground**にはさまざまなオプションがあります。それぞれのオプションは、AIモデルとの対話や利用方法を異なるアプローチで提供し、特定のニーズに合わせて調整できます。

このラボでは、以下のPlaygroundsを主に使用します：

1. **Chat Playground**
2. **Images Playground**
3. **Real-time audio playground**
4. **Agents playground**

![Azure AI Foundry Playgroundsの画像](../../../../lab/Workshop Instructions/Images/aifoundry-playgrounds.jpeg)

### Chat Playground

Playgroundセクション内で、**Chat Playground**に移動し、**Try the Chat Playground**を選択します。この機能では、さまざまなAIモデルと会話形式で対話し、テストできます。

![Azure AI Foundry Playground Chat Modeの画像](../../../../lab/Workshop Instructions/Images/aifoundry-chat-playground.jpeg)

1. **Deployment**: デプロイされたモデルを切り替えることができます。
2. **System Message Box**: ユーザーが操作を開始する前に、モデルに指示を入力する場所です。
3. **Add your data**: Azure AI Foundryポータルは、外部データを提供してモデルの検索能力や文脈を向上させることをサポートします。
4. **Parameters**: モデルの詳細設定（例：温度）を含むタブです。
5. **Chat Box**: モデルとのやり取りがチャット形式で表示されます。
6. **Prompt Box**: モデルに送信したいプロンプトを入力する場所です。

### Images Playground

Playgroundsに戻り、**Image Playground**を選択して**Try the Image Playground**をクリックします。このオプションでは、画像生成を行うことができます。

![Azure AI Foundry Playground Images Modeの画像](../../../../lab/Workshop Instructions/Images/aifoundry-image-playground.jpeg)

1. **Deployments**: 画像生成用のモデルを選択できるドロップダウンです。これらのモデルは、チャット用モデルと同様にデプロイメントから提供されます。
2. **Prompt Box**: チャットPlaygroundのプロンプトボックスと同様に、ユーザーが生成したい画像の説明を入力する場所です。
3. **Results Box**: 生成された画像がここに表示されます。

### Real-time audio playground

Playgroundsに戻り、**Real-time audio playground**を選択して**Try the Real-time audio Playground**をクリックします。この機能では、音声形式でAIモデルと対話し、テストすることができます。

![Azure AI Foundry Playground Real time audio modeの画像](../../../../lab/Workshop Instructions/Images/aifoundry-real-time-audio.jpeg)

1. **Deployment**: デプロイされたモデルを切り替えることができます。
2. **Server turn detection**: サーバーが音声活動検出（VAD）を使用して、ユーザーが話し終えたタイミングを特定するかどうかを決定します。
3. **System Message Box**: ユーザーが操作を開始する前に、モデルに指示を入力する場所です。
4. **Choose a voice**: gpt-4o-realtimeは、さまざまなアクセントや音調の音声を選択できます。
5. **Server turn detection**: 音声活動検出を改善し、モデルの効率とパフォーマンスを最適化する追加パラメーター。
6. **Parameters**: モデルの詳細設定（例：温度、最大応答）を含むタブです。
7. **Prompt Button**: チャットPlaygroundのプロンプトボックスと同様に、ユーザーが入力を行う場所です。

## Agents playground

ナビゲーションバーで**Agents**を選択します。この機能では、AI駆動のエージェントを構築、テスト、カスタマイズするためのツールを提供します。

![Azure AI Foundry Playground Agents Modeの画像](../../../../lab/Workshop Instructions/Images/agents-playground-pt1.jpeg)

最初のエージェントを作成すると、以下のUIコンポーネントが表示されます：
1. **Agent id and name:** エージェントに名前を付けることができます。
2. **Deployment**: 画像生成用のモデルを選択できるドロップダウンです。これらのモデルは、チャット用モデルと同様にデプロイメントから提供されます。
3. **Instructions Box:** ユーザーが操作を開始する前に、モデルに指示を入力する場所です。

![](../../../../lab/Workshop Instructions/Images/agents-playground-pt2.jpeg)

4. **Knowledge:** エージェントにデータソースへのアクセスを許可し、回答の根拠を提供します。
5. **Actions:** 実行時にさまざまなツールを使用することで、エージェントの能力を拡張します。
6. **Model settings**: モデルの詳細設定（例：温度、Top P）を含むタブです。
7. **Prompt Box:** チャットPlaygroundのプロンプトボックスと同様に、ユーザーが入力を行う場所です。

## 準備完了

これで、Azure AI Foundryの必要なセットアップと基本をカバーしました。次に進み、モデルとの対話を開始します。

**プロジェクトPlayground**内の**Chat**に戻り、指示に従って[Part 1: Text Generation](./02_Text_Generation.md)に進んでください。

> [!IMPORTANT]
> **Chat Playground**に戻り、[Part 1: Text Generation](./02_Text_Generation.md)に進んでください。

**免責事項**:  
この文書は、機械翻訳AIサービスを使用して翻訳されています。正確性を追求していますが、自動翻訳にはエラーや不正確な部分が含まれる可能性があります。元の言語で作成された原文を信頼できる情報源としてお考えください。重要な情報については、専門の人間による翻訳をお勧めします。本翻訳の使用に起因する誤解や解釈の相違について、当社は一切の責任を負いません。