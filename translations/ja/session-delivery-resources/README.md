## 使用方法

ようこそ、

> 以下のリソースは、セッションを学び、実施するためにプレゼンターが利用することを目的としています。

あなたがここに来てくださったことを嬉しく思います。この素晴らしいコンテンツをお届けいただけるのを楽しみにしています。経験豊富なプレゼンターであるあなたには、プレゼンテーションの「方法」はすでにご存じだと思いますので、このガイドでは「何を」プレゼンテーションする必要があるかに焦点を当てます。プレゼンテーションデザインチームによって作成された内容の全体像を提供します。

プレゼンテーションの動画とともに、このドキュメントでは、PowerPointスライドやデモの手順、コードなど、プレゼンテーションを成功させるために必要なすべてのアセットへのリンクを提供します。

1. ドキュメント全体を読むこと。
<!-- 1. プレゼンテーション動画を視聴すること -->
1. リードプレゼンターに質問すること。

## ファイル概要

| リソース             | リンク                              | 説明 |
|-------------------|----------------------------------|-------------------|
| PowerPoint        | [Presentation](https://aka.ms/AAryqzi) | スライド |
| セッション配信リソースPPT録画     | [Video](https://aka.ms/AAs7etz) | セッション配信リソースPowerPointスライドの録画 |
| セッション配信リソースPowerPoint |  [Deck](https://aka.ms/AAs7mfu) | このワークショップ用のセッション配信リソーススライド |
| ワークショップ手順 |  [Video](/lab/Workshop%20Instructions/00_Introduction.md) | LLMとの対話方法に関するステップバイステップの手順 |
| Skillableワークショップ手順 |  [Video](/lab/Skillable%20Workshop%20Instructions/00_Introduction.md) | Skillableラボの手順 |

## 始めるにあたって

このリポジトリは以下のセクションに分かれています：

| [Slides](https://aka.ms/AAryqzi) | [Skillableワークショップ手順](/lab/Skillable%20Workshop%20Instructions/00_Introduction.md) | [Skillable以外のワークショップ手順](/lab/Workshop%20Instructions/00_Introduction.md) | 
|-------------------|---------------------------|--------------------------------------|
| 35スライド  | 4パート - 15分 | [Skillable以外でのワークショップ実施方法](/lab/Workshop%20Instructions/00_Introduction.md) |

## スライド

[スライド](https://aka.ms/AAryqzi)には、各セッション部分にプレゼンターノートが含まれています。

### タイミング

> [NOTE!]
> ワークショップでは、Q&Aは通常ワークショップ中に行われます。この5分を削って、より実践的な時間に充てることもできます。

| 時間        | 説明 
--------------|-------------
0:00 - 3:00   | セッションのイントロダクション 
3:00 - 15:00  | 大規模言語モデル（LLM）の仕組み 
15:00 - 30:00 | テキスト生成
30:00 - 45:00 | 画像生成とマルチモダリティ
45:00 - 65:00 | Azure AIアシスタント
70:00 - 75:00 | 重要なポイントのまとめ

### ワークショップの実施形式

- このワークショップでは、最初の15分を使って、LLMの仕組みについてスライドを説明します。
- 残りの時間は、参加者が個別にワークショップに取り組み、必要に応じてサポートを提供します。
- 最後に、最終スライドを共有し、セッションを締めくくります。

## Skillableでのワークショップ手順

[ツールとその使用方法の概要はこちらで確認できます](/lab/Skillable%20Workshop%20Instructions/01_Set_up.md)。

| セクション | 分数 | 
-------------------------------------------------------------------------------------------------------|---------|
|  [1 - Azure AI Foundryの紹介](/lab/Skillable%20Workshop%20Instructions/01_Set_up.md) | 10       | 
|  [2 - テキスト生成](/lab/Skillable%20Workshop%20Instructions/02_Text_Generation.md) | 15   |
|  [3 - 画像生成](/lab/Skillable%20Workshop%20Instructions/03_Image_Generation.md) | 10   | [Link](../../../session-delivery-resources) | 15       | 
|  [4 - マルチモダリティ](/lab/Skillable%20Workshop%20Instructions/04_Multimodal_Interfaces.md) | 10  | 
|  [5 - AIアシスタント](/lab/Skillable%20Workshop%20Instructions/05_AI_Assistants.md) | 15  | [Link](../../../session-delivery-resources)  |

## Skillable以外でのワークショップ実施方法

Skillableを利用せずにこのセッションを実施する場合、参加者が以下の要件を満たしていることを確認してください：

- Azureサブスクリプション - [無料で作成する。](https://azure.microsoft.com/free/cognitive-services?WT.mc_id=aiml-132569-bethanycheum)
- Azure OpenAIリソース - [GPT-4oおよびDALL.E 3モデルがサポートされている地域で利用可能。](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models#assistants-preview?WT.mc_id=aiml-132569-bethanycheum) 推奨地域は**スウェーデン中央**です。

Azureにリソースをデプロイするには、**Deploy to Azure**ボタンをクリックするだけです。

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2Faitour-interact-with-llms%2Fmain%2Flab%2FWorkshop%20Instructions%2Fassets%2FAITour24_WKR540_Template.json)

すべてのワークショップ手順は[こちら](/lab/Workshop%20Instructions/00_Introduction.md)で確認できます。

**免責事項**:  
この文書は、AI翻訳サービスを使用して機械翻訳されたものです。正確性を期すよう努めておりますが、自動翻訳には誤りや不正確な部分が含まれる可能性があります。元の言語で記載された原文が正式な情報源として考慮されるべきです。重要な情報については、専門の人間による翻訳を推奨します。本翻訳の利用により生じた誤解や誤った解釈について、当方は一切の責任を負いません。