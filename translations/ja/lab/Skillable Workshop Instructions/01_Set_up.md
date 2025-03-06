# はじめに

> [!TIP]
> **Azure AI Foundry**とは何ですか？Azure AI Foundryは、未来を創造するための革新的なプラットフォームです。Azure AIの幅広い機能とツールを提供し、AIアプリケーションやエージェントの設計、カスタマイズ、管理を可能にします。GitHub、Visual Studio、Copilot Studioなど、開発者に愛されるツールとシームレスに統合されています。Azure AI Foundryは、開発者やIT管理者がAIのビジョンを簡単かつ効率的に実現するための力を提供します。

## Windowsにサインインする
最初のステップとして、以下の資格情報を使用してラボの仮想マシンにログインしてください：
- ユーザー名：Adminに設定済み。
- パスワード：+++@lab.VirtualMachine(Win11Base23B-W11-22H2).Password+++を入力してクリックします。

> [!TIP]
> **Skillable**を初めて使用しますか？緑色の「T」（例：+++Admin+++）は、現在のVMのカーソル位置にワンクリックで自動入力される値を示します。これにより、手間が削減され、入力エラーが最小限に抑えられます。

## Azure AI Foundryポータルにサインインする

このワークショップでは、Azure AI Foundryポータルを使用し、特にプレイグラウンド機能に焦点を当てます。

1. デスクトップ上の**Microsoft Edge**ブラウザをクリックします。Azure AI Foundryポータルのホームページが表示されている2番目のブラウザタブに移動します。

![Azure AI Foundryのホームページ](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-homepage.jpeg)

## Azure AI Foundryポータルのナビゲーション

1. まず、**サインイン**をクリックします。ウィンドウの右上にサインインリンクがあります。ログイン資格情報を求められたら、以下の情報を入力してください：
    - メールアドレス：+++@lab.CloudPortalCredential(User1).Username+++
    - パスワード：+++@lab.CloudPortalCredential(User1).Password+++

    ログインが完了したら、プラットフォームをナビゲートし始めましょう。

2. 利用可能なハブのリストから**Workshop AI Hub**を見つけます。**ハブ内のプロジェクトをクリック**して、その設定とリソースにアクセスします。

![ハブ管理タブ](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-hub-navigation.jpeg)

## プロジェクト

![プロジェクト概要タブ](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-project-overview.jpeg)

### プロジェクト概要

このページでは、Azure AI Foundryポータルプロジェクトの概要を見ることができます。以下を含みます：
- **プロジェクト名と説明**：プロジェクトの名前と簡単な説明。
- **プロジェクト詳細**：プロジェクトの接続文字列、場所、リソースグループなどのさまざまなプロパティのコレクション。
- **エンドポイントとキー**：Azure AI Foundryポータルでは、複数のリソースを接続して機能を拡張できます。Azure OpenAI、Azure AI Search、Azure AI Servicesなどのリソースがプロジェクトの機能をさらに強化し、LLMのデプロイメントやベクター検索などの機能を利用可能にします。ここでは、*APIエンドポイントとキー*やドキュメントなどの有用な情報を見つけることができます。
- **最近のリソースとチュートリアル**：最近使用したリソースがハイライトされ、学習リソースやチュートリアルが追加で提供されます。

### ナビゲーションバー

ナビゲーションバーに新しいタブが追加されていることに気づくでしょう。これらはプロジェクトに関連する機能を表しています。

![プロジェクトナビゲーションバー](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-project-navigation.jpeg)

新しいセクションは以下の通りです：
1. 最初のセクションには、_Playgrounds_（モデルと対話するための場所）、_Overview_（プロジェクトの概要）、_Model Catalog_（Azure AI Foundry内の利用可能なモデルを表示）、_AI Services_（Azure AI Servicesのリスト、デモ、ユースケースなど）が含まれます。
1. **構築とカスタマイズ**：クラウドコンピュートを使用してコードを実行したり、[_Prompt Flow_](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow)にアクセスしたり、デプロイメントの微調整を行ったりすることで、プロジェクトの範囲を広げるためのオプションがあります。
1. **評価と改善**：モデルの_Evaluations_を開発したり、フローをデバッグするための_tracing_、プロンプト入力や出力を制御するための_content filters_を追加したりできます。
1. **マイアセット**：_データ_、_インデックス_、_モデルとエンドポイント_、_Webアプリ_など、プロジェクトに追加要素を加えることができます。
1. **管理センター**：ハブやプロジェクトの詳細とリソースを管理するための場所です。

このラボでは**Playgrounds**を使用します。Playgroundsに移動して次のセクションに進みましょう。

## Playgrounds

**Playground**にはさまざまなオプションがあります。各オプションは、特定のニーズに合わせてAIモデルと対話し、使用するための異なるアプローチを表しています。

このPlaygroundsで主に作業するのは以下のオプションです：
1. **Chat Playground**
1. **Images Playground**
1. **Real-time audio playground**
1. **Agents playground**

![Azure AI Foundry Playgroundsの画像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-playgrounds.jpeg)

### Chat Playground

Playgroundセクション内で**Chat playground**に移動し、**Try the Chat Playground**を選択します。この機能を使用すると、会話形式でさまざまなAIモデルと対話し、テストすることができます。

![Azure AI Foundry Playground Chatモードの画像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-playground.jpeg)

1. **デプロイメント**：ここでデプロイ済みのモデルを切り替えることができます。
1. **システムメッセージボックス**：ユーザーと対話する前に、モデルに指示を入力する場所です。
1. **データを追加**：Azure AI Foundryポータルは、外部データをモデルに提供することをサポートしており、より良い検索とコンテキストを提供します。
1. **パラメーター**：温度など、モデルの詳細設定が含まれています。
1. **チャットボックス**：モデルとの対話がチャットメッセージ形式で表示されます。
1. **プロンプトボックス**：モデルに送信したいプロンプトを入力する場所です。

### Images Playground

Playgroundsに戻り、**Image playground**を選択して**Try the Image Playground**をクリックします。このオプションでは、画像生成を行うことができます。

![Azure AI Foundry Playground Imagesモードの画像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-image-playground.jpeg)

1. **デプロイメント**：このドロップダウンで画像生成用のモデルを選択します。これらのモデルはチャット用のモデルと同様にデプロイメントから提供されます。
1. **プロンプトボックス**：チャットプレイグラウンドのボックスと同様に、ユーザーが生成したい画像の説明を入力します。
1. **結果ボックス**：生成された画像がここに表示されます。

### Real-time audio playground

Playgroundsに戻り、**Real-time audio playground**を選択して**Try the Real-time audio Playground**をクリックします。この機能を使用すると、音声会話形式でさまざまなAIモデルと対話し、テストすることができます。

![Azure AI Foundry Playground Real time audioモードの画像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-real-time-audio.jpeg)

1. **デプロイメント**：ここでデプロイ済みのモデルを切り替えることができます。
1. **サーバーターン検出**：サーバーが音声活動検出（VAD）を使用して、ユーザーが話し終えたタイミングを識別するかどうかを決定します。
1. **システムメッセージボックス**：ユーザーと対話する前に、モデルに指示を入力する場所です。
1. **声を選択**：gpt-4o-realtimeは、好みに応じてユニークなアクセントやトーンを持つさまざまな声を提供します。
1. **追加パラメーター**：音声活動検出を改善し、モデルの効率とパフォーマンスを最適化するための設定です。
1. **パラメーター**：温度や最大応答など、モデルの詳細設定が含まれています。
1. **プロンプトボタン**：チャットプレイグラウンドのボックスと同様に、ユーザーがモデルに送信する入力を指定します。

## Agents playground

ナビゲーションバーで**Agents**を選択します。この機能では、AI駆動エージェントを構築、テスト、カスタマイズするためのツールを提供します。

![Azure AI Foundry Playground Agentsモードの画像](../../../../lab/Skillable Workshop Instructions/Images/agents-playground-pt1.jpeg)

最初のエージェントを作成すると、UIコンポーネントは以下のように表示されます：
1. **エージェントIDと名前**：エージェントに名前を付けることができます。
1. **デプロイメント**：このドロップダウンで画像生成用のモデルを選択します。これらのモデルはチャット用のモデルと同様にデプロイメントから提供されます。
1. **指示ボックス**：ユーザーと対話する前に、モデルに指示を入力する場所です。

![](../../../../lab/Skillable Workshop Instructions/Images/agents-playground-pt2.jpeg)

4. **知識**：エージェントにデータソースへのアクセスを与え、応答を強化します。
1. **アクション**：エージェントが実行時にさまざまなツールを使用できるようにして、機能を拡張します。
1. **モデル設定**：温度やTop Pなど、モデルの詳細設定が含まれています。
1. **プロンプトボックス**：チャットプレイグラウンドのボックスと同様に、ユーザーがモデルに送信する入力を指定します。

## スタートの準備

これで、Azure AI Foundryポータルの必要なセットアップと基本事項をカバーしました。それでは、モデルとの対話を開始しましょう。

- **Playgrounds**に移動し、**Chat playground**を選択して**Try the Chat Playground**をクリックします。  
- _指示タブ_で、次に進むには「Next」をクリックしてパート1：テキスト生成に進んでください。

「Next」をクリックしてテキスト生成セクションに進みます。

**免責事項**:  
この文書は、機械翻訳AIサービスを使用して翻訳されています。正確性を追求していますが、自動翻訳には誤りや不正確な箇所が含まれる場合があります。原文（元の言語の文書）を信頼できる正式な情報源としてお考えください。重要な情報については、専門の人間による翻訳をお勧めします。本翻訳の使用に起因する誤解や解釈の誤りについて、当社は一切の責任を負いません。