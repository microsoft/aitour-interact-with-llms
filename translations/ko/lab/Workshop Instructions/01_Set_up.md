# 시작하기

> [!TIP]
> **Azure AI Foundry**란 무엇인가요? Azure AI Foundry는 혁신가들이 미래를 창조할 수 있도록 돕는 궁극의 플랫폼입니다. 이 플랫폼은 AI 애플리케이션과 에이전트를 설계, 맞춤화, 관리할 수 있는 Azure AI의 포괄적인 기능과 도구를 제공합니다. GitHub, Visual Studio, Copilot Studio를 포함한 전 세계적으로 사랑받는 개발자 도구와 원활하게 통합되어 있습니다. Azure AI Foundry는 개발자와 IT 관리자가 쉽고 효율적으로 AI 비전을 실현할 수 있도록 지원합니다.

## 사전 준비 사항

실습을 완료하려면 다음이 필요합니다:

- Azure 구독 - [무료로 생성하기](https://azure.microsoft.com/free/cognitive-services?WT.mc_id=aiml-132569-bethanycheum)
- [지원 지역에서 GPT-4o 및 DALL.E 3 모델을 사용할 수 있는 Azure OpenAI 리소스](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/models#assistants-preview?WT.mc_id=aiml-132569-bethanycheum)

## 리소스 배포하기

이 워크숍에서는 Azure AI Foundry를 사용할 것입니다. 먼저 아래 단계를 따라 필요한 리소스를 배포하세요:

1. 리소스를 배포하려면 Azure 버튼을 클릭하세요: [![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fmicrosoft%2Faitour-interact-with-llms%2Fmain%2Flab%2FWorkshop%20Instructions%2Fassets%2FAITour24_WKR540_Template.json)

2. 새로 열린 탭에서 Azure 계정에 로그인하세요.

3. 로그인 후, 사용자 지정 템플릿을 기반으로 리소스를 생성할 수 있는 페이지로 리디렉션됩니다. 새 리소스 그룹을 생성하고 이름을 **interact-with-llms**로 설정하세요.

4. **Unique Suffix** 필드에 고유한 4자리 문자를 입력하세요. 완료되면 **Review and Create** 버튼을 클릭하여 리소스를 생성하세요.

> [!NOTE]
> 리소스 배포는 약 2-3분 정도 소요됩니다.

5. 배포가 완료되면, 브라우저에서 Azure AI Foundry로 이동하여 [https://ai.azure.com](https://ai.azure.com?WT.mc_id=aiml-132569-bethanycheum) 링크를 방문하세요.

## Azure AI Foundry 탐색하기

![Azure AI Foundry 로그인 후 홈 화면](../../../../lab/Workshop Instructions/Images/ai-Foundry-login-homepage.png)

1. 먼저, 왼쪽 사이드바에서 **Management** 섹션을 찾으세요. 이 섹션 아래에서 **All Resources**를 선택하세요. 이 작업을 통해 사용 가능한 모든 리소스와 도구가 표시되는 중앙화된 영역으로 이동하여 현재 허브 연결 상태를 한눈에 볼 수 있습니다.

> [!NOTE]
> **All Resources** 섹션을 찾을 수 없는 경우, **All Hubs** 섹션을 클릭하세요.

2. 사용 가능한 허브 목록에서 **Workshop AI Hub**를 찾으세요. 해당 허브와 연결된 프로젝트를 **클릭**하여 설정 및 리소스에 액세스하세요.

![허브 관리 탭](../../../../lab/Workshop Instructions/Images/aifoundry-hub-navigation.jpeg)

## 프로젝트

![프로젝트 개요 탭](../../../../lab/Workshop Instructions/Images/aifoundry-project-overview.jpeg)

### 프로젝트 개요

이 페이지에서는 Azure AI Foundry 포털 프로젝트의 개요를 확인할 수 있습니다. 여기에는 다음이 포함됩니다:
- **프로젝트 이름 및 설명**: 프로젝트의 이름과 Azure AI Foundry 포털 프로젝트에 대한 간단한 설명.
- **프로젝트 세부 정보**: 프로젝트의 연결 문자열, 위치, 리소스 그룹 등 다양한 속성 모음.
- **엔드포인트 및 키**: Azure AI Foundry 포털은 여러 리소스를 연결할 수 있어 기능을 확장합니다. Azure OpenAI, Azure AI Search, Azure AI Services와 같은 리소스를 통해 LLM 배포나 벡터 검색과 같은 기능을 사용할 수 있습니다. 여기에서 *API 엔드포인트 및 키*와 문서를 확인할 수 있습니다.
- **최근 리소스 및 튜토리얼**: 최근 리소스와 추가 학습 자료 및 튜토리얼이 강조 표시되어 시작하는 데 도움을 줍니다.

### 탐색 바

탐색 바에는 프로젝트와 관련된 기능을 나타내는 새 탭이 추가된 것을 볼 수 있습니다.

![프로젝트 탐색 바](../../../../lab/Workshop Instructions/Images/aifoundry-project-navigation.jpeg)

새로운 섹션은 다음과 같습니다:
1. **Playgrounds**: 모델과 상호작용할 수 있는 공간, 프로젝트의 개요를 제공하는 _Overview_, Azure AI Foundry 내 사용 가능한 모델을 보여주는 _Model Catalog_, 데모, 사용 사례 등을 포함한 Azure AI Services 목록을 확인할 수 있는 _AI Services_가 포함됩니다.
1. **Build and Customize**: 클라우드 컴퓨팅 실행, [_Prompt Flow_](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow) 접근, 배포에 대한 _Fine Tuning_ 수행과 같은 프로젝트 확장 기능을 제공합니다.
1. **Assess and Improve**: 모델에 대한 _Evaluations_ 개발, 흐름 디버깅을 위한 _Tracing_, 입력 및 출력에 가드레일을 추가하는 _Content Filters_를 포함합니다.
1. **My Assets**: _데이터_, _인덱스_, _모델 및 엔드포인트_, _웹 앱_과 같은 리소스를 프로젝트에 추가할 수 있습니다.
1. **Management Center**: 모든 허브 및 프로젝트 세부 정보와 리소스를 관리할 수 있는 위치입니다.

이번 실습에서는 **Playgrounds**를 사용합니다. Playgrounds로 이동하여 다음 섹션으로 진행하세요.

## Playgrounds

**Playground**에서는 다양한 옵션을 확인할 수 있습니다. 각 옵션은 AI 모델과 상호작용하고 사용하는 다양한 접근 방식을 나타내며, 특정 요구 사항에 맞게 조정할 수 있습니다.

이번 실습에서는 주로 다음 Playgrounds에서 작업합니다:

1. **Chat Playground**
1. **Images Playground**
1. **Real-time audio playground**
1. **Agents Playground**

![Azure AI Foundry Playgrounds 이미지](../../../../lab/Workshop Instructions/Images/aifoundry-playgrounds.jpeg)

### Chat Playground

Playground 섹션 내에서 **Chat Playground**로 이동하여 **Try the Chat Playground**를 선택하세요. 이 기능은 대화 형식으로 다양한 AI 모델과 상호작용하고 테스트할 수 있도록 합니다.

![Azure AI Foundry Chat 모드 이미지](../../../../lab/Workshop Instructions/Images/aifoundry-chat-playground.jpeg)

1. **Deployment**: 배포된 모델 간 전환이 가능합니다.
1. **System Message Box**: 사용자와 상호작용하기 전에 모델에 대한 지침을 입력하는 공간입니다.
1. **Add your data**: Azure AI Foundry 포털은 외부 데이터를 제공하여 모델의 검색 및 컨텍스트를 향상시킬 수 있습니다.
1. **Parameters**: 온도와 같은 모델의 세부 설정을 포함합니다.
1. **Chat Box**: 모델과의 대화 메시지가 표시됩니다.
1. **Prompt Box**: 모델에 보낼 프롬프트를 입력하는 공간입니다.

### Images Playground

Playgrounds로 돌아가 **Image Playground**를 선택한 후 **Try the Image Playground**를 클릭하세요. 이 옵션은 이미지 생성 작업을 수행할 수 있습니다.

![Azure AI Foundry 이미지 모드](../../../../lab/Workshop Instructions/Images/aifoundry-image-playground.jpeg)

1. **Deployments**: 이미지 생성을 위한 모델을 선택할 수 있습니다. 이러한 모델은 Chat 모델과 마찬가지로 배포에서 가져옵니다.
1. **Prompt Box**: Chat Playground의 프롬프트 상자와 유사하게, 생성하고자 하는 이미지에 대한 설명을 입력하는 공간입니다.
1. **Results Box**: 생성된 이미지가 표시됩니다.

### Real-time audio playground

Playgrounds로 돌아가 **Real-time audio playground**를 선택한 후 **Try the Real-time audio Playground**를 클릭하세요. 이 기능은 오디오 대화 형식으로 AI 모델과 상호작용하고 테스트할 수 있도록 합니다.

![Azure AI Foundry 실시간 오디오 모드](../../../../lab/Workshop Instructions/Images/aifoundry-real-time-audio.jpeg)

1. **Deployment**: 배포된 모델 간 전환이 가능합니다.
1. **Server turn detection**: 사용자가 말을 마쳤을 때 음성 활동 감지(VAD)를 사용할지 결정합니다.
1. **System Message Box**: 사용자와 상호작용하기 전에 모델에 대한 지침을 입력하는 공간입니다.
1. **Choose a voice**: gpt-4o-realtime은 다양한 악센트와 음색을 제공하여 사용자의 선호에 맞게 선택할 수 있습니다.
1. **Server turn detection**: 음성 활동 감지를 최적화하여 모델의 효율성과 성능을 향상시킵니다.
1. **Parameters**: 온도 및 최대 응답과 같은 모델의 세부 설정을 포함합니다.
1. **Prompt Button**: Chat Playground의 프롬프트 상자와 유사하게, 모델에 보낼 입력을 제공하는 공간입니다.

## Agents Playground

탐색 바에서 **Agents**를 선택하세요. 이 기능은 AI 기반 에이전트를 구축, 테스트 및 사용자 지정할 수 있는 도구를 제공합니다.

![Azure AI Foundry Agents 모드](../../../../lab/Workshop Instructions/Images/agents-playground-pt1.jpeg)

처음 에이전트를 생성한 후 UI 구성 요소는 다음과 같습니다:
1. **Agent id와 이름**: 에이전트의 이름을 지정할 수 있습니다.
1. **Deployment**: 이미지 생성을 위한 모델을 선택할 수 있습니다.
1. **Instructions Box**: 사용자와 상호작용하기 전에 모델에 대한 지침을 입력하는 공간입니다.

![](../../../../lab/Workshop Instructions/Images/agents-playground-pt2.jpeg)

4. **Knowledge**: 에이전트가 응답을 기반으로 할 데이터 소스에 접근할 수 있도록 합니다.
1. **Actions**: 실행 시간에 다양한 도구를 사용할 수 있도록 에이전트의 기능을 확장합니다.
1. **Model settings**: 온도 및 Top P와 같은 모델의 세부 설정을 포함합니다.
1. **Prompt Box**: Chat Playground의 프롬프트 상자와 유사하게, 모델에 보낼 입력을 제공하는 공간입니다.

## 시작할 준비 완료

이제 Azure AI Foundry의 기본 설정과 개요를 다루었습니다. 이제 모델과 상호작용을 시작하겠습니다.

**Chat** 아래의 **Project Playground**로 돌아가 지침의 Next를 클릭하여 Part 1: Text Generation으로 진행하세요.

> [!IMPORTANT]
> **Chat Playground**로 돌아가 [Part 1: Text Generation](./02_Text_Generation.md)으로 이동하세요.

**면책 조항**:  
이 문서는 기계 기반 AI 번역 서비스를 사용하여 번역되었습니다. 정확성을 위해 노력하고 있지만, 자동 번역에는 오류나 부정확성이 포함될 수 있습니다. 원어로 작성된 원본 문서를 신뢰할 수 있는 권위 있는 자료로 간주해야 합니다. 중요한 정보의 경우, 전문적인 인간 번역을 권장합니다. 이 번역 사용으로 인해 발생하는 오해나 잘못된 해석에 대해 당사는 책임을 지지 않습니다.