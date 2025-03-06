# 요약  
잘하셨습니다! 워크숍의 끝까지 오셨고, 생성형 AI의 힘을 활용하여 Contoso Outdoor Company를 위한 전자상거래 웹사이트 디자인을 성공적으로 구축하셨습니다.

## 리소스 정리  

튜토리얼을 마친 후, 생성한 모든 리소스를 삭제하고 싶으실 수 있습니다. 개별적으로 리소스를 삭제하거나, 전체 리소스 그룹을 삭제할 수 있습니다.

1. [Azure Portal](https://portal.azure.com)에 접속합니다.  
2. 홈페이지에서 **Resource groups**로 이동한 후, 우리가 생성한 리소스 그룹 **interact-with-llms**를 선택합니다.  

![](../../../../lab/Workshop Instructions/Images/azure-portal-resource-group.PNG)

3. 리소스 그룹 상단 네비게이션 패널에서 **Delete resource group**을 선택합니다.  

![](../../../../lab/Workshop Instructions/Images/delete-resource-group-navigation.PNG)

4. 리소스 그룹 삭제를 확인하기 위해 리소스 그룹 이름을 입력하라는 메시지가 표시됩니다. **interact-with-llms**를 입력한 후 **Delete**를 클릭하여 리소스 그룹을 삭제합니다.  

![Deleting resource Group](../../../../lab/Workshop Instructions/Images/delete-resource-group-name.PNG)

5. 리소스 그룹이 삭제되었다는 알림을 받게 됩니다.  

![](../../../../lab/Workshop Instructions/Images/delete-resource-group-notification-popup.PNG)

## 기억해야 할 주요 사항  
- 생성형 AI 모델은 사람처럼 텍스트, 이미지, 코드를 생성할 수 있습니다.  
- 생성형 AI 모델은 상태를 유지하지 않습니다. 즉, 학습하지 않으며 고정된 시점의 학습 데이터에 의해 제한됩니다.  
- Azure OpenAI Service는 최첨단 자연어 생성형 AI 모델(GPT-4, GPT-4 turbo, GPT-4o)을 보안성과 엔터프라이즈 수준의 약속과 함께 제공하는 관리형 서비스입니다.  
- Azure AI Foundry는 Azure AI 포털과 통합된 SDK 경험을 비롯하여, 사전 구축된 앱 템플릿 및 3P ISV 도구 및 서비스에 대한 액세스를 제공하는 Azure의 통합 AI 플랫폼입니다.  
- 프롬프트 엔지니어링은 생성형 AI 모델의 "기반"을 다지는 기술로, 모델 출력의 스타일을 조정하고 사실 정보를 제공하며 의도하지 않은 동작을 제한하는 데 사용됩니다.  
- Azure AI Agents는 데이터를 분석하고, 솔루션을 제안하며, 도구를 통합하여 작업을 자동화하는 복잡한 코파일럿과 같은 경험을 가진 애플리케이션을 개발자들이 더 쉽게 만들 수 있도록 돕는 새로운 기능입니다.  

## 추가 자료  
Azure OpenAI Service와 Azure AI Foundry에 대해 더 깊이 배우기 위한 몇 가지 리소스를 소개합니다:  

- Microsoft Learn 모듈: [Azure OpenAI Service 소개](https://learn.microsoft.com/en-us/training/modules/explore-azure-openai/?WT.mc_id=aiml-132569-cacaste)  
- [Azure OpenAI Service 문서](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/?WT.mc_id=aiml-132569-cacaste)  
- [Azure OpenAI Service 가격](https://azure.microsoft.com/en-us/products/cognitive-services/openai-service/#pricing/?WT.mc_id=aiml-132569-cacaste)  
- [Azure OpenAI Service의 투명성 노트](https://learn.microsoft.com/en-us/legal/cognitive-services/openai/transparency-note/?WT.mc_id=aiml-132569-cacaste)는 Azure OpenAI 모델의 기능, 사용 사례 및 한계에 대한 세부 정보를 제공합니다.  
- [Azure AI Foundry와 RAG 패턴 구현 시작하기](https://learn.microsoft.com/training/paths/create-custom-copilots-ai-studio//?WT.mc_id=aiml-132569-cacaste)  
- [Azure AI Agents 시작하기](https://learn.microsoft.com/en-us/azure/ai-services/agents/overview)  

**면책 조항**:  
이 문서는 기계 기반 AI 번역 서비스를 사용하여 번역되었습니다. 정확성을 위해 최선을 다하고 있지만, 자동 번역에는 오류나 부정확성이 포함될 수 있습니다. 원본 문서를 해당 언어로 작성된 상태에서 권위 있는 출처로 간주해야 합니다. 중요한 정보의 경우, 전문적인 인간 번역을 권장합니다. 이 번역 사용으로 인해 발생하는 오해나 잘못된 해석에 대해 당사는 책임을 지지 않습니다.