## 사용 방법

환영합니다,

> 다음 자료는 발표자가 세션을 학습하고 전달하는 데 필요한 내용을 담고 있습니다.

이 놀라운 콘텐츠를 전달하기 위해 오신 것을 환영합니다. 숙련된 발표자로서 이미 "어떻게" 발표해야 하는지 알고 계실 거라 믿습니다. 따라서 이 가이드는 "무엇을" 발표해야 하는지에 중점을 둡니다. 발표 디자인 팀이 준비한 발표 자료를 전체적으로 이해할 수 있도록 안내합니다.

발표 영상과 함께, 성공적인 발표를 위해 필요한 모든 자료(예: PowerPoint 슬라이드, 데모 지침 및 코드)로 연결되는 링크도 제공합니다.

1. 문서를 처음부터 끝까지 읽으세요.
<!-- 1. 발표 영상을 시청하세요. -->
1. 리드 발표자에게 질문하세요.

## 파일 요약

| 리소스             | 링크                              | 설명             |
|-------------------|----------------------------------|-------------------|
| PowerPoint        | [Presentation](https://aka.ms/AAryqzi) | 슬라이드 |
| 세션 전달 리소스 PPT 녹화본 | [Video](https://aka.ms/AAs7etz) | 세션 전달 리소스 PowerPoint 슬라이드의 녹화본 |
| 세션 전달 리소스 PowerPoint | [Deck](https://aka.ms/AAs7mfu) | 워크숍용 세션 전달 리소스 슬라이드 |
| 워크숍 지침        | [Video](/lab/Workshop%20Instructions/00_Introduction.md) | LLM과 상호작용하는 단계별 지침 |
| Skillable 워크숍 지침 | [Video](/lab/Skillable%20Workshop%20Instructions/00_Introduction.md) | Skillable 실습 지침 |

## 시작하기

이 저장소는 다음 섹션으로 나뉩니다:

| [Slides](https://aka.ms/AAryqzi) | [Skillable 워크숍 지침](/lab/Skillable%20Workshop%20Instructions/00_Introduction.md) | [Skillable이 아닌 워크숍 지침](/lab/Workshop%20Instructions/00_Introduction.md) | 
|-------------------|---------------------------|--------------------------------------|
| 35 슬라이드 | 4파트 - 15분 | [Skillable 외부에서 워크숍 실행](/lab/Workshop%20Instructions/00_Introduction.md) |

## 슬라이드

[슬라이드](https://aka.ms/AAryqzi)에는 세션 각 부분에 대한 발표자 노트가 포함되어 있습니다.

### 시간 관리

> [NOTE!]
> 워크숍의 경우, Q&A는 보통 워크숍 진행 중에 이루어집니다. 이 5분을 실습 시간을 늘리는 데 활용할 수 있습니다.

| 시간         | 설명 
--------------|-------------
0:00 - 3:00   | 세션 소개 
3:00 - 15:00  | 대규모 언어 모델의 작동 원리 
15:00 - 30:00 | 텍스트 생성
30:00 - 45:00 | 이미지 생성 및 멀티모달리티
45:00 - 65:00 | Azure AI 어시스턴트
70:00 - 75:00 | 주요 행사 요약

### 워크숍 전달 형식

- 이 워크숍에서는 처음 15분 동안 슬라이드를 통해 LLM의 작동 방식을 설명하세요.
- 나머지 시간 동안 참석자들이 워크숍을 개별적으로 진행하도록 하고, 필요할 때 도움을 제공하세요.
- 마지막에는 최종 슬라이드를 공유하고 세션을 마무리하세요.

## Skillable에서의 워크숍 지침

[여기서 도구와 사용 방법에 대한 개요를 확인할 수 있습니다](/lab/Skillable%20Workshop%20Instructions/01_Set_up.md).

| 섹션 | 소요 시간 | 
-------------------------------------------------------------------------------------------------------|---------|
|  [1 - Azure AI Foundry 소개](/lab/Skillable%20Workshop%20Instructions/01_Set_up.md) | 10분       | 
|  [2 - 텍스트 생성](/lab/Skillable%20Workshop%20Instructions/02_Text_Generation.md) | 15분   |
|  [3 - 이미지 생성](/lab/Skillable%20Workshop%20Instructions/03_Image_Generation.md) | 10분   | [링크](../../../session-delivery-resources) | 15분       | 
|  [4 - 멀티모달리티](/lab/Skillable%20Workshop%20Instructions/04_Multimodal_Interfaces.md) | 10분  | 
|  [5 - AI 어시스턴트](/lab/Skillable%20Workshop%20Instructions/05_AI_Assistants.md) | 15분  | [링크](../../../session-delivery-resources)  |

## Skillable 외부에서 워크숍 실행

Skillable 접근 없이 세션을 전달하려면, 참석자가 실습을 완료할 때 다음 요구 사항을 충족하도록 하세요:

- Azure 구독 - [무료로 생성하세요.](https://azure.microsoft.com/free/cognitive-services?WT.mc_id=aiml-132569-bethanycheum)
- [GPT-4 및 DALL.E 3 모델이 지원되는 Azure OpenAI 리소스](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models#assistants-preview?WT.mc_id=aiml-132569-bethanycheum)가 지원되는 지역. 권장 지역은 **스웨덴 중앙**입니다.

Azure에 리소스를 배포하려면, **Deploy to Azure** 버튼을 클릭하세요.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2Faitour-interact-with-llms%2Fmain%2Flab%2FWorkshop%20Instructions%2Fassets%2FAITour24_WKR540_Template.json)

모든 워크숍 지침은 [여기](/lab/Workshop%20Instructions/00_Introduction.md)에서 확인할 수 있습니다.

**면책 조항**:  
이 문서는 기계 기반 AI 번역 서비스를 사용하여 번역되었습니다. 정확성을 위해 노력하고 있지만, 자동 번역에는 오류나 부정확성이 포함될 수 있습니다. 원본 문서를 해당 언어로 작성된 상태에서 권위 있는 자료로 간주해야 합니다. 중요한 정보의 경우, 전문적인 인간 번역을 권장합니다. 이 번역 사용으로 인해 발생하는 오해나 잘못된 해석에 대해 당사는 책임을 지지 않습니다.