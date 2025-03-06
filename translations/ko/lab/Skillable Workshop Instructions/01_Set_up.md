# 시작하기

> [!TIP]
> **Azure AI Foundry**란 무엇인가요? Azure AI Foundry는 혁신가들이 미래를 창조할 수 있도록 돕는 궁극의 플랫폼입니다. Azure AI의 종합적인 기능과 도구를 제공하여 AI 애플리케이션 및 에이전트를 설계, 맞춤화, 관리할 수 있습니다. GitHub, Visual Studio, Copilot Studio와 같은 세계적으로 사랑받는 개발 도구와 매끄럽게 통합되어 있습니다. Azure AI Foundry는 개발자와 IT 관리자가 손쉽고 효율적으로 AI 비전을 실현할 수 있도록 지원합니다.

## Windows에 로그인하기
첫 번째 단계로, 다음 자격 증명을 사용하여 실습용 가상 머신에 로그인하세요:
- 사용자 이름: Admin으로 설정되어 있습니다.
- 비밀번호: +++@lab.VirtualMachine(Win11Base23B-W11-22H2).Password+++를 입력하고 클릭하세요.

> [!TIP]
> **Skillable을 처음 사용하시나요?** 초록색 "T" (예: +++Admin+++)는 현재 가상 머신의 커서 위치에 한 번의 클릭으로 자동 입력되는 값을 나타냅니다. 이를 통해 작업을 줄이고 입력 오류를 최소화할 수 있습니다.

## Azure AI Foundry 포털에 로그인하기

이번 워크숍에서는 Azure AI Foundry 포털, 특히 플레이그라운드 기능을 중점적으로 다룰 것입니다.

1. 데스크톱에서 **Microsoft Edge** 브라우저를 클릭하세요. 두 번째 브라우저 탭으로 이동하면 아래 이미지와 같이 Azure AI Foundry 포털 홈페이지가 표시됩니다.

![Azure AI Foundry 홈페이지](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-homepage.jpeg)

## Azure AI Foundry 포털 탐색하기

1. 먼저 **로그인(Sign In)**을 클릭하세요. 창 오른쪽 상단에서 로그인 링크를 찾을 수 있습니다. 로그인 자격 증명이 요청되면 다음 정보를 입력하세요:
    - 이메일: +++@lab.CloudPortalCredential(User1).Username+++
    - 비밀번호: +++@lab.CloudPortalCredential(User1).Password+++

    이제 로그인했으니 플랫폼 탐색을 시작할 수 있습니다.

2. 사용 가능한 허브 목록에서 **Workshop AI Hub**를 찾으세요. 허브와 함께 표시된 **프로젝트를 클릭**하여 설정과 리소스에 접근하세요.

![허브 관리 탭](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-hub-navigation.jpeg)

## 프로젝트

![프로젝트 개요 탭](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-project-overview.jpeg)

### 프로젝트 개요

이 페이지에서는 Azure AI Foundry 포털 프로젝트의 개요를 확인할 수 있습니다. 여기에는 다음이 포함됩니다:
- **프로젝트 이름 및 설명**: 프로젝트 이름과 Azure AI Foundry 포털 프로젝트의 간략한 설명.
- **프로젝트 세부정보**: 프로젝트의 연결 문자열, 위치, 리소스 그룹 등 다양한 속성 모음.
- **엔드포인트와 키**: Azure AI Foundry 포털은 여러 리소스를 연결할 수 있어 기능과 성능을 확장합니다. Azure OpenAI, Azure AI Search, Azure AI Services와 같은 리소스는 LLM 배포나 벡터 검색과 같은 기능을 제공하여 프로젝트의 역량을 더욱 강화합니다. 여기서 *API 엔드포인트와 키* 및 관련 문서를 확인할 수 있습니다.
- **최근 리소스 및 튜토리얼**: 최근 사용한 리소스가 강조 표시되며, 추가 학습 리소스와 시작을 돕는 튜토리얼도 제공됩니다.

### 탐색 바

탐색 바에는 프로젝트와 관련된 새로운 탭이 추가되어 있습니다.

![프로젝트 탐색 바](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-project-navigation.jpeg)

새로운 섹션은 다음과 같습니다:
1. _Playgrounds_ (모델과 상호작용), _Overview_ (프로젝트의 일반적인 개요 제공), _Model Catalog_ (Azure AI Foundry 내 사용 가능한 모델 목록), _AI Services_ (데모, 사용 사례 등 Azure AI Services 목록 제공).
2. **Build and Customize**: 클라우드 컴퓨팅 실행, [_Prompt Flow_](https://learn.microsoft.com/en-us/azure/ai-studio/how-to/prompt-flow) 접근, 배포의 _Fine Tuning_과 같은 프로젝트 확장 기능 제공.
3. **Assess and Improve**: 모델 평가 개발, 플로우 디버깅을 위한 _Tracing_, 프롬프트 입력 및 출력에 가드레일을 추가하는 _Content Filters_ 포함.
4. **My assets**: _데이터_, _인덱스_, _모델과 엔드포인트_, _웹 애플리케이션_과 같은 추가 리소스를 프로젝트에 추가 가능.
5. **Management Center**: 모든 허브 및 프로젝트 세부정보와 리소스를 관리하는 위치.

이번 실습에서는 **Playgrounds**를 사용합니다. Playgrounds로 이동하여 다음 섹션으로 진행하세요.

## Playgrounds

**Playground**에는 여러 옵션이 있습니다. 각 옵션은 AI 모델과 상호작용하고 사용하는 다양한 접근 방식을 나타내며, 특정 요구 사항에 맞게 조정할 수 있습니다.

이번 실습에서는 다음과 같은 Playground에서 주로 작업합니다:

1. **Chat Playground**
2. **Images Playground**
3. **Real-time audio playground**
4. **Agents playground**

![Azure AI Foundry Playgrounds 이미지](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-playgrounds.jpeg)

### Chat Playground

Playground 섹션에서 **Chat playground**로 이동한 후 **Try the Chat Playground**를 선택하세요. 이 기능을 통해 다양한 AI 모델과 대화 형식으로 상호작용하고 테스트할 수 있습니다.

![Azure AI Foundry Playground Chat 모드 이미지](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-playground.jpeg)

1. **배포(Deployment)**: 배포된 모델 간 전환이 가능합니다.
2. **시스템 메시지 박스**: 사용자 상호작용 전에 모델에 지시를 입력하는 곳입니다.
3. **데이터 추가(Add your data)**: 외부 데이터를 제공하여 검색 및 컨텍스트를 향상시킬 수 있습니다.
4. **매개변수(Parameters)**: 온도와 같은 모델의 세부 설정을 포함합니다.
5. **채팅 박스(Chat Box)**: 모델과의 상호작용이 채팅 메시지 형태로 표시됩니다.
6. **프롬프트 박스(Prompt Box)**: 모델에 보낼 프롬프트를 입력하는 곳입니다.

### Images Playground

Playgrounds로 돌아가 **Image playground**를 선택한 후 **Try the Image Playground**를 클릭하세요. 이 옵션을 통해 이미지 생성 작업을 수행할 수 있습니다.

![Azure AI Foundry Playground Images 모드 이미지](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-image-playground.jpeg)

1. **배포(Deployments)**: 이미지 생성을 위한 모델 선택이 가능합니다. 이 모델들은 채팅 모델과 마찬가지로 배포된 리소스에서 가져옵니다.
2. **프롬프트 박스(Prompt Box)**: 생성하고자 하는 이미지에 대한 설명을 입력하는 곳입니다.
3. **결과 박스(Results Box)**: 생성된 이미지가 표시되는 곳입니다.

### Real-time audio playground

Playgrounds로 돌아가 **Real-time audio playground**를 선택한 후 **Try the Real-time audio Playground**를 클릭하세요. 이 기능은 오디오 대화 형식으로 다양한 AI 모델과 상호작용하고 테스트할 수 있습니다.

![Azure AI Foundry Playground Real time audio 모드 이미지](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-real-time-audio.jpeg)

1. **배포(Deployment)**: 배포된 모델 간 전환이 가능합니다.
2. **서버 턴 감지(Server turn detection)**: 사용자가 말하기를 끝냈을 때 음성 활동 감지(VAD)를 사용할지 여부를 결정합니다.
3. **시스템 메시지 박스**: 사용자 상호작용 전에 모델에 지시를 입력하는 곳입니다.
4. **음성 선택(Choose a voice)**: gpt-4o-realtime은 다양한 억양과 톤을 가진 음성을 제공합니다.
5. **매개변수(Parameters)**: 온도와 최대 응답 등 모델의 세부 설정을 포함합니다.
6. **프롬프트 버튼(Prompt Button)**: 모델에 보낼 프롬프트를 입력하는 곳입니다.

## Agents playground

탐색 바에서 **Agents**를 선택하세요. 이 기능은 AI 기반 에이전트를 구축, 테스트, 사용자 정의할 수 있는 도구를 제공합니다.

![Azure AI Foundry Playground Agents 모드 이미지](../../../../lab/Skillable Workshop Instructions/Images/agents-playground-pt1.jpeg)

첫 번째 에이전트를 생성하면 다음과 같은 UI 구성 요소를 볼 수 있습니다:
1. **에이전트 ID와 이름**: 에이전트의 이름을 지정할 수 있습니다.
2. **배포(Deployment)**: 이미지 생성을 위한 모델 선택이 가능합니다.
3. **지시 박스(Instructions Box)**: 사용자 상호작용 전에 모델에 지시를 입력하는 곳입니다.

![](../../../../lab/Skillable Workshop Instructions/Images/agents-playground-pt2.jpeg)

4. **지식(Knowledge)**: 에이전트가 응답을 보강할 수 있도록 데이터 소스에 접근할 수 있습니다.
5. **액션(Actions)**: 실행 시 다양한 도구를 사용할 수 있도록 에이전트의 기능을 확장합니다.
6. **모델 설정(Model settings)**: 온도 및 Top P와 같은 모델의 세부 설정을 포함합니다.
7. **프롬프트 박스(Prompt Box)**: 모델에 보낼 프롬프트를 입력하는 곳입니다.

## 시작 준비

이로써 Azure AI Foundry 포털의 필수 설정과 기본 사항을 다루었습니다. 이제 모델과 상호작용을 시작합니다.

- **Playgrounds**로 이동하여 **Chat playground**를 선택한 후 **Try the Chat Playground**를 클릭하세요.
- _Instructions_ 탭에서 **다음(Next)**을 클릭하여 Part 1: Text Generation으로 진행하세요.

**다음(Next)**을 클릭하여 텍스트 생성 섹션으로 진행하세요.

**면책 조항**:  
이 문서는 기계 기반 AI 번역 서비스를 사용하여 번역되었습니다. 정확성을 위해 최선을 다하고 있지만, 자동 번역에는 오류나 부정확성이 포함될 수 있습니다. 원어로 작성된 원본 문서를 권위 있는 출처로 간주해야 합니다. 중요한 정보의 경우, 전문적인 인간 번역을 권장합니다. 이 번역 사용으로 인해 발생하는 오해나 잘못된 해석에 대해 당사는 책임을 지지 않습니다.