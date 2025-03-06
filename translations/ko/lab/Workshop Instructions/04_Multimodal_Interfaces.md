# Part 3 - 멀티모달

지금까지 우리는 텍스트를 입력하고 텍스트나 이미지를 출력받는 단일 모달리티로 LLM과 상호작용해왔습니다. 하지만 텍스트, 이미지, 음성 등 여러 모달리티를 활용해 모델과 상호작용할 수 있는 멀티모달 인터페이스가 점점 더 인기를 얻고 있습니다. 이를 통해 인간-컴퓨터 간 상호작용이 더욱 개선됩니다. 이번 섹션에서는 **GPT-4o mini**와 **GPT-4o audio**를 활용해 멀티모달 인터페이스로 상호작용하는 방법을 살펴보겠습니다.

> [!TIP]  
> **GPT-4o mini**는 자연어 처리와 시각적 이해를 결합한 멀티모달 모델입니다. 텍스트와 이미지를 조합한 입력을 처리할 수 있으며, 두 모달리티와 관련된 출력을 생성할 수 있습니다.

**GPT-4o realtime**은 저지연의 "음성 입력, 음성 출력" 대화형 상호작용을 지원합니다. 이는 고객 지원, 음성 비서, 실시간 번역기와 같은 라이브 상호작용이 필요한 사용 사례에 적합합니다.

## 모범 사례

- **문맥적 구체성**: 현재 상황에 대한 문맥을 추가하면 모델이 적절한 출력을 이해하는 데 도움이 됩니다. 이 구체성은 관련된 측면에 집중하고 불필요한 세부사항을 피하는 데 유용합니다.

- **작업 중심 프롬프트**: 특정 작업에 초점을 맞추면 모델이 해당 관점을 고려하여 출력을 생성하는 데 도움이 됩니다.

- **출력 형식 정의**: 출력에 필요한 형식(예: markdown, JSON, HTML 등)을 명확히 언급하세요. 또한 응답의 특정 구조, 길이 또는 속성을 제안할 수도 있습니다.

- **거부 처리**: 모델이 작업 수행 불가능을 나타낼 때 프롬프트를 수정하는 것이 효과적인 해결책이 될 수 있습니다. 더 구체적인 프롬프트는 모델이 더 명확하게 이해하고 작업을 잘 수행할 수 있도록 안내합니다. 다음 팁을 참고하세요:
    - 생성된 응답에 대한 설명을 요청하여 모델 출력의 투명성을 높이기
    - 단일 이미지 프롬프트를 사용할 경우, 이미지를 텍스트보다 먼저 배치
    - 모델에게 이미지를 먼저 상세히 설명한 후, 설명을 기반으로 특정 작업 수행 요청하기

- **프롬프트 튜닝**: 텍스트 생성 시나리오에서 탐구했던 프롬프트 튜닝 기법을 시도해보세요. 예를 들어:
    - 요청을 세분화하기 (예: 사고의 연쇄)
    - 예시 추가하기 (예: 소수샷 학습)

## 이미지로 모델과 상호작용하기

1. **playgrounds** 섹션으로 이동하여 **Try the Chat Playground**를 선택합니다.

>[!alert] 시작하기 전에, 이전 상호작용의 문맥을 피하기 위해 **Clear Chat**을 클릭하세요.

2. 채팅 텍스트 상자에서 첨부 아이콘을 클릭하여 로컬 이미지를 업로드합니다.

![이미지 업로드 입력](../../../../lab/Workshop Instructions/Images/upload_image_icon.png)

3. 데스크탑의 ```house-multimodal``` 폴더에 있는 모든 이미지를 선택하세요.  
4. 파일을 업로드한 후, 다음 프롬프트를 시도해 이미지를 활용한 상호작용을 시작하세요:

```
Create a tagline and short description for this rental home advertisement.
- The first picture is from the home
- The other pictures are from sights nearby
- In the description use the features of the house and make the ad more compelling with the sights. 
- Do not talk about features not visible in the images.
- If you have information about the location of the images, use that information in the description
```

## 문맥 제공

다음 데모에서는 가려진 이미지를 사용합니다. 이미지는 전체 문맥을 가리기 위해 의도적으로 경계 상자가 추가되었습니다.

1. _채팅 초기화_ 후, 채팅 텍스트 상자에 다음 프롬프트를 추가합니다: ``what is that?``  
2. 첨부 아이콘을 클릭하고 데스크탑 폴더로 이동하여 [context-001](./Images/context-001.png) 이미지를 업로드한 후 프롬프트를 전송합니다.

> 만약 제가 '이게 뭔가요?'라고 물었다면, 텍스트를 식별하는 데 어려움을 겪을 수 있습니다. 이는 명확하지 않고 고립된 단어를 해독하는 고전적인 컴퓨터 비전 문제를 보여줍니다. gpt-4o-mini를 사용해 '이게 뭔가요?'라고 물어보면, '글씨체가 손글씨 스타일이라 명확히 읽을 수 없습니다. “Mark”일 수 있습니다.'라고 응답합니다. 또한 '텍스트 일부가 가려져 읽을 수 없습니다.'라는 점도 언급합니다.

3. 새로운 이미지를 추가합니다. 데스크탑 폴더로 이동하여 [context-002](./Images/context-002.png) 이미지를 업로드하고 프롬프트 ```Extract all the texts from the image. Explain what you think this is.```를 사용합니다.

> 조금 더 정보를 공개했지만 여전히 식별하기 어렵습니다. 이번에는 프롬프트를 약간 조정하여 '이미지에서 모든 텍스트를 추출하세요. 이게 무엇이라고 생각하나요?'라고 합니다. gpt-4o-mini는 '이것은 "milk, steak"라고 쓰여 있으며 쇼핑 목록처럼 보입니다.'라고 응답합니다. 또한 이미지가 여전히 부분적으로 가려져 있다는 점을 언급하는 것도 흥미롭습니다.

4. 마지막 이미지를 추가합니다. 데스크탑 폴더로 이동하여 [context-003](./Images/demo-4-context-003.png) 이미지를 업로드하고 프롬프트 ```Extract all the texts from the image. Explain what you think this is.```를 사용합니다.

> 전체 이미지를 공개한 결과, gpt-4o-mini의 추측이 정확했습니다. 이는 실제로 쇼핑 목록이며, 'mayo'와 'organic bread' 같은 항목을 정확히 식별합니다. 더 흥미로운 점은 맥주 항목에 대한 메모를 해석한 것입니다. 이는 '맥주 항목에 대한 메모는 주의나 양 제한에 대한 강조를 나타냅니다.'라고 미묘한 문맥을 포착합니다.

## 실시간 음성 상호작용

**gpt-4o-realtime-preview** 모델을 통합하면 사용자가 음성 명령을 사용해 플랫폼과 상호작용할 수 있어 쇼핑 경험이 더욱 재미있고 접근 가능해집니다.

1. **Playgrounds**로 돌아가 **try Real-time audio playground**를 선택하고 배포를 **gpt-4o-realtime-preview**로 설정합니다.

2. **model instructions box**에 다음을 업데이트합니다:

    ```You are a pirate, and every response must be full of pirate lingo. ```

3. Playground에서 **enable microphone**을 클릭하면 팝업이 나타납니다. 상호작용을 위해 오디오를 활성화하려면 허용을 클릭합니다.

![AI Foundry에서 오디오 활성화](../../../../lab/Workshop Instructions/Images/aifoundry-enable-audio.jpeg)

4. **start listening** 버튼을 클릭하고 ``hello``를 말한 뒤 모델에게 몇 가지 사실을 물어보며 상호작용합니다.

5. 다음으로, 시스템 메시지를 아래와 같이 변경한 뒤 모델과 다시 상호작용합니다:

```You are a valiant medieval knight. Every response should echo the chivalry, honor, and grandeur of the court. Speak with formality and grace, as if addressing kings, queens, and noble warriors.```

## 다음 단계

축하합니다! 이제 실습의 3번째 부분을 완료하고 멀티모달 모델과 상호작용하는 방법을 배웠습니다.

[Part 4: Azure AI Agents](./05_AI_Agents.md)로 이동하세요.

**면책 조항**:  
이 문서는 기계 기반 AI 번역 서비스를 사용하여 번역되었습니다. 정확성을 위해 노력하고 있지만, 자동 번역에는 오류나 부정확성이 포함될 수 있습니다. 원문이 작성된 언어의 문서를 권위 있는 원본으로 간주해야 합니다. 중요한 정보의 경우, 전문적인 인간 번역을 권장합니다. 이 번역 사용으로 인해 발생하는 오해나 오역에 대해 당사는 책임을 지지 않습니다.