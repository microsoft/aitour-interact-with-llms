# Part 3 - 멀티모달

지금까지 우리는 텍스트를 입력하고 텍스트나 이미지를 출력받는 단일 모달리티로 LLM과 상호작용해왔습니다. 그러나 텍스트, 이미지, 음성 등 여러 모달리티를 활용하여 모델과 상호작용할 수 있는 멀티모달 인터페이스가 점점 더 인기를 얻고 있습니다. 이러한 인터페이스는 인간-컴퓨터 상호작용을 개선합니다. 이 섹션에서는 **GPT-4o mini**와 **GPT-4o audio**를 사용하여 멀티모달 인터페이스로 상호작용하는 방법을 탐구합니다.

> [!TIP]  
> **GPT-4o mini**는 자연어 처리와 시각적 이해를 결합한 멀티모달 모델입니다. 텍스트와 이미지를 조합하여 입력받고, 두 모달리티 모두에 관련된 출력을 생성할 수 있습니다.

**GPT-4o realtime**은 낮은 지연 시간으로 "음성 입력, 음성 출력" 대화를 지원합니다. 고객 지원 에이전트, 음성 비서, 실시간 번역기와 같은 실시간 상호작용이 필요한 사용 사례에 적합합니다.

## 모범 사례

- **맥락의 구체성**: 현재 상황에 대한 맥락을 추가하면 모델이 적절한 출력을 더 잘 이해할 수 있습니다. 이러한 구체성은 관련된 측면에 초점을 맞추고 불필요한 세부 정보를 피하는 데 도움을 줍니다.

- **작업 중심의 프롬프트**: 특정 작업에 초점을 맞추면 모델이 해당 관점을 고려하여 출력을 생성하도록 도울 수 있습니다.

- **출력 형식 정의**: 출력에 원하는 형식을 명확히 명시하세요. 예: Markdown, JSON, HTML 등. 또한 특정 구조, 길이 또는 응답에 대한 특정 속성을 제안할 수 있습니다.

- **거부 처리**: 모델이 작업 수행 불가를 표시할 경우 프롬프트를 수정하는 것이 효과적인 해결책이 될 수 있습니다. 더 구체적인 프롬프트는 모델이 명확히 이해하고 더 잘 수행하도록 안내할 수 있습니다. 몇 가지 팁은 다음과 같습니다:
  - 생성된 응답에 대한 설명을 요청하여 모델 출력의 투명성을 높이세요.
  - 단일 이미지 프롬프트를 사용할 경우, 이미지를 텍스트 앞에 배치하세요.
  - 모델에게 먼저 이미지를 자세히 설명하도록 요청한 후, 설명에서 특정 작업을 완료하도록 하세요.

- **프롬프트 튜닝**: 텍스트 생성 시나리오에서 살펴본 프롬프트 튜닝 기술을 시도하세요. 예:
  - 요청을 세분화하기 (예: 사고의 사슬)
  - 예제 추가하기 (예: 소수 샷 학습)

## 이미지를 사용하여 모델과 상호작용하기

1. **playgrounds** 섹션으로 이동하여 **Try the Chat Playground**를 선택하세요.

>[!alert] 시작하기 전에 **Clear Chat**을 클릭하여 이전 상호작용에서 남은 컨텍스트를 제거하세요.

2. 채팅 텍스트 상자에서 첨부 아이콘을 클릭하여 로컬 이미지를 업로드하세요.

![이미지 업로드 아이콘](../../../../lab/Skillable Workshop Instructions/Images/upload_image_icon.png)

3. 데스크톱의 ```house-multimodal``` 폴더에서 모든 이미지를 선택하세요.  
4. 파일을 업로드한 후, 다음 프롬프트를 사용하여 이미지와 상호작용을 시작해 보세요:

```
Create a tagline and short description for this rental home advertisement.
- The first picture is from the home
- The other pictures are from sights nearby
- In the description use the features of the house and make the ad more compelling with the sights. 
- Do not talk about features not visible in the images.
- If you have information about the location of the images, use that information in the description
```

## 맥락 제공하기

다음 데모에서는 가려진 이미지를 사용합니다. 이미지에 경계 상자를 추가하여 전체 맥락을 의도적으로 가렸습니다.

1. _채팅 기록을 지우고_ 채팅 텍스트 상자에 다음 프롬프트를 추가하세요: ``what is that?``  
2. 첨부 아이콘을 클릭하고 데스크톱 폴더에서 [context-001](./Images/context-001.png) 이미지를 업로드한 후 프롬프트를 전송하세요.

> 만약 제가 '이게 뭐야?'라고 묻는다면, 이 텍스트를 식별하기 어려울 수 있습니다. 이는 컴퓨터 비전의 전형적인 문제 중 하나인 광학 문자 인식에서 흐릿하고 고립된 단어를 해독하는 어려움을 보여줍니다. 이제 gpt-4o-mini를 사용하여 '이게 뭐야?'라고 물어보면, '이 텍스트는 손글씨 스타일로 인해 명확히 읽히지 않습니다. "Mark"처럼 보일 수 있습니다.'라고 응답합니다. 또한, '텍스트의 일부는 가려져 읽을 수 없습니다.'라는 점도 언급합니다.

3. 새로운 이미지를 추가합니다. 데스크톱 폴더에서 [context-002](./Images/context-002.png) 이미지를 업로드하고 프롬프트 ```Extract all the texts from the image. Explain what you think this is.```를 사용하세요.

> 약간 더 노출되었지만, 여전히 무엇인지 식별하기는 어렵습니다. 이번에는 프롬프트를 약간 조정하여 '이미지에서 모든 텍스트를 추출하세요. 이게 무엇인지 설명하세요.'라고 요청합니다. gpt-4o-mini는 '이것은 "milk, steak"라고 쓰여 있으며, 쇼핑 목록으로 보입니다.'라고 응답합니다. 또한, 이미지가 여전히 부분적으로 가려져 있다는 점을 언급하는 점이 흥미롭습니다.

4. 마지막 이미지를 추가합니다. 데스크톱 폴더에서 [context-003](./Images/demo-4-context-003.png) 이미지를 업로드하고 프롬프트: ```Extract all the texts from the image. Explain what you think this is.```를 사용하세요.

> 전체 이미지를 드러내면, gpt-4o-mini가 맞았음을 알 수 있습니다. 실제로 쇼핑 목록이었습니다. 'mayo', 'organic bread'와 같은 항목을 정확히 식별합니다. 더 흥미로운 점은 맥락을 해석하는 방식입니다. 맥주 항목에 대한 메모를 언급하며, '메모는 절제 또는 양을 제한하라는 강조로 보입니다.'라고 설명합니다.

## 실시간 음성 상호작용

**gpt-4o-realtime-preview** 모델을 통합하면 사용자가 음성 명령을 사용하여 플랫폼과 상호작용할 수 있어 쇼핑 경험이 더욱 흥미롭고 접근 가능해집니다.

1. **Playgrounds**로 돌아가 **try Real-time audio playground**를 선택하고 배포를 **gpt-4o-realtime-preview**로 설정하세요.

2. **모델 지침 상자**를 다음과 같이 업데이트하세요:

    ```You are a pirate, and every response must be full of pirate lingo. ```

3. Playground에서 **마이크 활성화**를 클릭하세요. 팝업이 나타나면 상호작용을 위해 오디오를 활성화하도록 허용을 클릭하세요.

![AI Foundry에서 오디오 활성화](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-enable-audio.jpeg)

4. **start listening** 버튼을 클릭하고 ``hello``라고 말하며 모델에게 몇 가지 사실을 물어보세요.

5. 다음으로 시스템 메시지를 다음과 같이 변경하고 모델과 다시 상호작용하세요:

```You are a valiant medieval knight. Every response should echo the chivalry, honor, and grandeur of the court. Speak with formality and grace, as if addressing kings, queens, and noble warriors.```

## 다음 단계

축하합니다! 이제 실습의 3번째 부분을 완료했으며 멀티모달 모델과 상호작용하는 방법을 배웠습니다.

**Next**를 클릭하여 Azure AI Agents 섹션으로 진행하세요.

**면책 조항**:  
이 문서는 기계 기반 AI 번역 서비스를 사용하여 번역되었습니다. 정확성을 위해 노력하고 있지만, 자동 번역에는 오류나 부정확성이 포함될 수 있음을 유의하시기 바랍니다. 원본 문서의 해당 언어 버전이 권위 있는 자료로 간주되어야 합니다. 중요한 정보의 경우, 전문적인 인간 번역을 권장합니다. 이 번역 사용으로 인해 발생하는 오해나 잘못된 해석에 대해 당사는 책임을 지지 않습니다.