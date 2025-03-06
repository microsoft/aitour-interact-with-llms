# パート2: 画像生成

このワークショップのパート2へようこそ！ここでは、テキストから画像を生成するモデルであるDALL-E 3を使って学んでいきます。

> [!TIP]  
> **DALL-E 3とは？**  
> DALL-E 3は、**自然言語入力**からグラフィカルデータを生成できるニューラルネットワークベースのモデルです。簡単に言えば、DALL-E 3に**説明文**を提供すると、それに基づいた適切な画像を生成することができます。

## 初めての画像を作成する

最初の画像を作成するには、以下の手順に従ってください：

![画像生成の例を示す画像](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-image-generation.jpeg)

1. 左側のナビゲーションバーで**playgrounds**に移動し、**Try the Image Playground**を選択します。
2. Images playground内で、**Deployments**とラベル付けされたドロップダウンメニューを見つけてクリックします。リストから**dall-e-3**を選択してください。
3. Images playground内の_"Describe the image you want to create."_とラベル付けされたテキストボックスを見つけます。以下のプロンプト例から「T」をクリックすると（例：``here is a sample prompt``）、現在のカーソル位置に自動的に入力されます。
4. メッセージを入力すると、**Generate**ボタンが表示されます。このボタンをクリックして、画像説明をモデルに送信します。
5. クエリを送信した後、モデルが処理して応答するのを少し待ちます。応答は入力欄の下のウィンドウに表示されます。

まず、説明ボックスに基本的なプロンプトを入力し、**Generate**をクリックして画像を生成してみましょう：

```a watercolor painting of Chicago skyline```

これにより、次のような画像が生成されます：

![水彩画のスカイライン画像](../../../../lab/Skillable Workshop Instructions/Images/DALL·E%202024-11-14%2009.27.57%20-%20A%20watercolor%20painting%20of%20the%20Chicago%20skyline,%20showcasing%20iconic%20skyscrapers%20such%20as%20the%20Willis%20Tower%20and%20John%20Hancock%20Center.%20The%20city%20is%20bathed%20in%20so.webp)

DALL-E 3が生成する画像はオリジナルであり、キュレーションされた画像カタログから取得されるものではありません。言い換えれば、DALL-E 3は適切な画像を検索するシステムではなく、訓練されたデータに基づいて新しい画像を生成する人工知能（AI）モデルです。

### 具体的に記述する

詳細な記述は、より正確な応答を得るために重要です。テキスト生成と同様に、画像生成モデルも詳細な説明を提供することで大いに恩恵を受けます。

1. 例えば、以下のプロンプトを入力してみてください：

    ```A logo for an adventure brand```

2. 次に**Generate**を選択し、生成された画像を確認してください。

    ![冒険ブランドのロゴ画像](../../../../lab/Skillable Workshop Instructions/Images/Generate%20a%20logo%20for%20an%20adventure%20brand.png)

3. 次に、説明にさらに詳細を追加してプロンプトを変更してみましょう：

    ```A logo combining a tent silhouette and stars, with a rustic feel for an adventure brand.```

4. 再び**Generate**を選択し、結果を比較してください。

    ![テントと星を組み合わせた冒険ブランドのロゴ画像](../../../../lab/Skillable Workshop Instructions/Images/logo-with-stars.png)

### ベストプラクティス

DALL-E 3を使って効果的で正確な画像を作成するために、以下のベストプラクティスを参考にしてください：

1. **明確で詳細なプロンプト**: テキストプロンプトを明確かつ詳細に記述します。説明が具体的であればあるほど、DALL-E 3は要求に一致する画像を生成しやすくなります。対象、動作、環境、スタイル、重要な詳細などを含めてください。

2. **形容詞の活用**: 形容詞や副詞を使って、画像に持たせたい特性や感情、特徴を説明します。これにより、生成される画像がより理想に近いものになります。

3. **詳細と簡潔さのバランス**: 詳細は重要ですが、過度に複雑または矛盾するプロンプトはAIを混乱させ、予期しない結果を招く可能性があります。コンテキストを十分に提供しつつ、簡潔さを保つよう心がけてください。

4. **さまざまなスタイルの試行**: 特定の美的感覚を持たせたい場合は、芸術的スタイルや影響を指定してください。例えば、芸術的な画像をリクエストすることも可能です。

5. **反復的アプローチ**: 最初に生成された画像が完璧でない場合があります。それを出発点として、出力に基づいてプロンプトを反復的に修正し、理想に近づけていきましょう。

6. **アスペクト比と構図**: 画像の構図やアスペクト比に好みがある場合は、それをプロンプトに含めてください。例えば、横長の画像や、被写体が中心から外れた構図をリクエストすることができます。

7. **文化的・文脈的な参照**: 必要に応じて、文化的または歴史的な参照を含めて追加のコンテキストを提供し、画像生成プロセスをガイドします。

8. **責任あるAIの考慮**: プロンプトの内容が責任あるAIの観点から適切であることを確認してください。攻撃的な画像、ステレオタイプを助長する画像、または著作権を侵害する画像の生成は避けてください。

9. **テストと学習**: さまざまなプロンプトを試して、DALL-E 3がどのように説明を解釈するかを理解しましょう。この学習プロセスは、プロンプトの精度を向上させるのに役立ちます。

10. **ガイドラインの遵守**: プロンプト作成時には、OpenAIの利用ケースポリシーとコンテンツガイドラインを遵守してください。OpenAIのコンテンツポリシーに反する画像のリクエストは避けてください。

## ブランドマスコットの作成

このワークショップでは、DALL-E 3の能力を活用して、フレンドリーな動物、ロボット、抽象的なキャラクターなど、さまざまなテーマのブランドマスコット画像を生成します。

また、DALL-E 3のさまざまなパラメーターをテストして、生成される画像の多様性を探ります。これらのパラメーターには以下が含まれます：

- **画像サイズ**: 正方形、横長、縦長など、異なるサイズを試して、キャンペーンでのデザインや使いやすさへの影響を理解します。
- **画像スタイル**: ナチュラルやビビッドなど、ブランドの個性に最も合うスタイルを試します。
- **画像品質**: 高解像度画像（印刷用）と低解像度画像（ウェブやソーシャルメディア用）の生成に適した品質設定を調整します。

1. まず、ブランドマスコットを生成してみましょう。以下のようなプロンプトを検討してください：

```A friendly robot mascot with a smiling face, designed in a cartoon style.```

![フレンドリーなロボットマスコットの画像](../../../../lab/Skillable Workshop Instructions/Images/robot-mascot-friendly.png)

```A playful fox mascot with a colorful scarf, representing agility and creativity.```

```An abstract figure with geometric shapes, conveying innovation and technology.```

2. Playground内で_ellipsisアイコン_をクリックし、設定に移動します。  
3. 各セクションのドロップダウン矢印をクリックしてパラメーターを変更します。  
4. 設定を更新した状態で再度プロンプトを試してみてください。

## 高度なプロンプト作成

基本的なプロンプトを見てきたので、新しい試みをしてみましょう。

>[!alert]  
> **システムメッセージを空にすることを忘れないでください。** 必要に応じて、**Reset to Default**をクリックするだけで初期状態に戻せます。

次に、gpt-4o-miniが生成したプロンプトを基に画像を作成してみます。

1. **Chat Playground**に戻ります。

2. **System message**の隣にある**Give the model instructions and context**欄の既存メッセージを消去し、システムメッセージを初期状態にリセットします。

3. **チャットボックス**に作成したい商品の詳細な説明を入力し、モデルにリクエストを送信します。

```
Generate a prompt for DALL-E 3 from this product description:

The 3D Animated Office Space Design by CreativeSpaces offers a modern, interactive representation of a professional work environment. This design concept includes ergonomic furniture, open and collaborative workspaces, greenery for a touch of nature, and large windows to maximize natural light. The layout also incorporates meeting pods, hot desks, and breakout areas for different work modes. The office has a neutral color palette, with accents of green and blue to create a calming yet productive atmosphere.

The 3D Animated Office Space Design is intended for use by architects, interior designers, and companies looking to revamp their workspaces. It highlights the importance of balancing privacy with collaboration, including quiet zones for focused work and shared areas for team interactions. The space features modern materials like glass and wood, combined with innovative lighting solutions to enhance productivity and employee well-being.

Beyond its aesthetic appeal, the 3D Animated Office Space Design is designed with functionality in mind. It includes ample storage solutions, acoustic panels to reduce noise, and modular furniture that can be rearranged to suit different needs. The green walls and potted plants throughout the office create a refreshing environment that promotes creativity and reduces stress. The design is presented in a high-quality 3D animation, providing a realistic walkthrough that allows clients to visualize the space effectively.
```

4. 応答が得られたら、応答の右上にある三点リーダーをクリックし、**Copy response to clipboard**を選択します。

![コピーオプションの画像](../../../../lab/Skillable Workshop Instructions/Images/ai-foundry-copy-response.png)

5. **Images playground**に戻り、**Deploymentsで'dall-e-3'が選択されていることを確認**した上で、生成されたプロンプトを**Prompt Box**に貼り付けます。

6. **Generate**をクリックし、どれほど詳細な画像が生成されるか確認してください。

![3Dワークスペースの画像](../../../../lab/Skillable Workshop Instructions/Images/_Create%20a%203D%20animation%20of%20a%20modern%20office%20space%20design%20featuring%20ergonomic%20furniture,%20collaborative%20workspaces,%20and%20greenery%20elements.%20The%20office%20should%20have%20large%20windows%20for%20natural%20light,%20meeting%20pods,%20an.png)

## 次のステップ

おめでとうございます！これでワークショップのパート2を完了し、さまざまな画像アセットを生成することができました。次のパートでは、マルチモーダルリクエストのためのモデルの使用方法を学びます。

**Next**をクリックして、マルチモーダリティセクションに進みましょう。

**免責事項**:  
この文書は、機械ベースのAI翻訳サービスを使用して翻訳されています。正確さを追求しておりますが、自動翻訳には誤りや不正確な部分が含まれる場合があります。原文（元の言語の文書）が公式かつ信頼できる情報源と見なされるべきです。重要な情報については、専門の人間による翻訳を推奨します。この翻訳の使用により生じた誤解や誤った解釈について、当方は一切の責任を負いません。