# 概要
お疲れさまでした！ワークショップを最後まで進め、Contoso Outdoor Company向けのeコマースウェブサイトデザインを、生成AIの力を活用して無事に構築することができました。

## リソースのクリーンアップ

チュートリアルを終えた後は、作成したすべてのリソースを削除することを検討してください。リソースを個別に削除することも、リソースグループ全体を削除することも可能です。

1. [Azure Portal](https://portal.azure.com) にアクセスします。
2. ホームページから **リソース グループ** に移動し、作成したリソースグループ **interact-with-llms** を選択します。

![](../../../../lab/Workshop Instructions/Images/azure-portal-resource-group.PNG)

3. リソースグループの上部ナビゲーションパネルで、**リソースグループの削除** を選択します。

![](../../../../lab/Workshop Instructions/Images/delete-resource-group-navigation.PNG)

4. 削除を確認するためにリソースグループ名を入力するよう求められます。名前 **interact-with-llms** を入力し、**削除** をクリックしてリソースグループを削除します。

![リソースグループの削除](../../../../lab/Workshop Instructions/Images/delete-resource-group-name.PNG)

5. リソースグループが削除されたことを示す通知が表示されます。

![](../../../../lab/Workshop Instructions/Images/delete-resource-group-notification-popup.PNG)

## 覚えておくべき重要なポイント
- 生成AIモデルは、人間らしいテキスト、画像、コードを生成できます。
- 生成AIモデルはステートレスであり、学習することはなく、トレーニングデータ（固定時点でのデータ）に制約されます。
- Azure OpenAI Service は、最先端の自然言語生成AIモデル（GPT-4、GPT-4 turbo、GPT-4oなど）へのアクセスを提供するマネージドサービスで、Azureのセキュリティとエンタープライズ向けの特長を備えています。
- Azure AI Foundry は、Azure AIポータルや統一されたSDKエクスペリエンスに加え、あらかじめ構築されたアプリテンプレートや3P ISVツールおよびサービスへのアクセスを提供する、Azureの統一AIプラットフォームです。
- プロンプトエンジニアリングは生成AIモデルを「基盤化」するための技術であり、モデルの出力スタイルに影響を与えたり、事実情報を提供したり、意図しない動作を制約するために使用できます。
- Azure AI Agents は、データを精査したり、解決策を提案したり、タスクを自動化したりする高度なコパイロットのような体験を持つアプリケーションを簡単に作成できる新しい機能です。

## 追加リソース
Azure OpenAI Service や Azure AI Foundry についてさらに学ぶための参考資料を以下に示します：

- Microsoft Learn モジュール: [Azure OpenAI Service 入門](https://learn.microsoft.com/en-us/training/modules/explore-azure-openai/?WT.mc_id=aiml-132569-cacaste)
- [Azure OpenAI Service ドキュメント](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/?WT.mc_id=aiml-132569-cacaste)
- [Azure OpenAI Service の価格](https://azure.microsoft.com/en-us/products/cognitive-services/openai-service/#pricing/?WT.mc_id=aiml-132569-cacaste)
- [Azure OpenAI Service の透明性に関するノート](https://learn.microsoft.com/en-us/legal/cognitive-services/openai/transparency-note/?WT.mc_id=aiml-132569-cacaste) には、Azure OpenAI モデルの機能、ユースケース、制限についての詳細が記載されています。
- [Azure AI Foundry を使った入門と RAG パターンの実装](https://learn.microsoft.com/training/paths/create-custom-copilots-ai-studio//?WT.mc_id=aiml-132569-cacaste)
- [Azure AI Agents の入門](https://learn.microsoft.com/en-us/azure/ai-services/agents/overview)

**免責事項**:  
この文書は、機械ベースのAI翻訳サービスを使用して翻訳されています。正確性を追求しておりますが、自動翻訳にはエラーや不正確な部分が含まれる場合があります。元の言語で記載された文書が正式な情報源として優先されるべきです。重要な情報については、専門の人間による翻訳を推奨します。本翻訳の使用により生じた誤解や解釈の違いについて、当方は一切の責任を負いかねます。