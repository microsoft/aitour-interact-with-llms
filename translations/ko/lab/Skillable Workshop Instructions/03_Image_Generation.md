# 2부: 이미지 생성

이 워크숍의 2부에 오신 것을 환영합니다. 여기에서는 텍스트-이미지 모델인 DALL-E 3와 상호작용해 보겠습니다.

> [!TIP]  
> DALL-E 3란 무엇인가요?  
> DALL-E 3는 **자연어 입력**으로부터 그래픽 데이터를 생성할 수 있는 신경망 기반 모델입니다. 간단히 말해, DALL-E 3에 **설명**을 제공하면 해당 설명에 적합한 이미지를 생성할 수 있습니다.

## 첫 번째 이미지 생성하기

첫 번째 이미지를 생성하려면 다음 단계를 따라주세요:

![이미지 생성 과정](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-image-generation.jpeg)

1. 왼쪽 탐색 메뉴에서 **Playgrounds**로 이동한 후, **Try the Image Playground**를 선택합니다.
2. Images Playground에서 **Deployments**라고 표시된 드롭다운 메뉴를 찾은 뒤, **dall-e-3**를 선택합니다.
3. Images Playground에서 _"Describe the image you want to create."_라는 텍스트 상자를 찾습니다. 아래의 프롬프트 예시에서 "T" (예: ``here is a sample prompt``)를 클릭하면 현재 커서 위치에 자동으로 입력됩니다.
4. 메시지를 입력한 후 **Generate** 버튼이 나타납니다. 버튼을 클릭해 이미지 설명을 모델에 제출하세요.
5. 요청을 제출한 후, 모델이 처리하고 응답할 때까지 잠시 기다립니다. 응답은 입력창 아래의 창에 나타납니다.

이제 설명 상자에 기본 프롬프트를 입력한 후, **Generate**를 클릭하여 이미지를 생성해 봅시다:

```a watercolor painting of Chicago skyline```

이렇게 하면 다음과 같은 이미지가 생성됩니다:

![수채화 스타일의 스카이라인](../../../../lab/Skillable Workshop Instructions/Images/DALL·E%202024-11-14%2009.27.57%20-%20A%20watercolor%20painting%20of%20the%20Chicago%20skyline,%20showcasing%20iconic%20skyscrapers%20such%20as%20the%20Willis%20Tower%20and%20John%20Hancock%20Center.%20The%20city%20is%20bathed%20in%20so.webp)

DALL-E 3가 생성한 이미지는 원본이며, 큐레이션된 이미지 카탈로그에서 검색된 것이 아닙니다. 즉, DALL-E 3는 적합한 이미지를 찾는 검색 시스템이 아니라, 학습된 데이터에 기반해 새로운 이미지를 생성하는 인공지능(AI) 모델입니다.

### 구체적으로 설명하기

세부적인 설명은 더 정확한 결과를 가져옵니다. 텍스트 생성과 마찬가지로, 이미지 생성 모델도 원하는 결과를 명확히 설명할수록 더 유용합니다.

1. 예를 들어, 다음 프롬프트를 입력해 보세요:

    ```A logo for an adventure brand```

2. 그런 다음 **Generate**를 선택하고 생성된 이미지를 확인합니다.

    ![모험 브랜드 로고](../../../../lab/Skillable Workshop Instructions/Images/Generate%20a%20logo%20for%20an%20adventure%20brand.png)

3. 이제 설명에 더 많은 세부사항을 추가하여 프롬프트를 수정해 봅시다:

    ```A logo combining a tent silhouette and stars, with a rustic feel for an adventure brand.```

4. 다시 **Generate**를 선택하고 결과를 비교합니다.

    ![텐트와 별을 결합한 로고](../../../../lab/Skillable Workshop Instructions/Images/logo-with-stars.png)

### 최적의 결과를 위한 팁

DALL-E 3로 효과적이고 정확한 이미지를 생성하려면 다음의 모범 사례를 따르세요:

1. **명확하고 상세한 프롬프트**: 텍스트 프롬프트를 명확하고 구체적으로 작성하세요. 설명이 구체적일수록 DALL-E 3가 요청에 부합하는 이미지를 생성할 가능성이 높아집니다. 주제, 동작, 환경, 스타일, 중요한 세부사항 등을 포함하세요.

1. **형용사 사용**: 형용사와 부사를 사용하여 이미지가 전달하길 원하는 특성, 감정, 특징 등을 설명하세요. 이를 통해 생성된 이미지가 더 정확히 비전에 부합할 수 있습니다.

1. **세부사항과 간결함의 균형**: 세부사항은 중요하지만, 지나치게 복잡하거나 모순된 프롬프트는 AI를 혼란스럽게 할 수 있습니다. 맥락을 충분히 제공하면서도 과도하게 복잡하지 않게 설명하세요.

1. **다양한 스타일 실험**: 특정 미적 감각을 원한다면 예술적 스타일이나 영향을 명시하세요. 예를 들어, 예술적인 이미지를 요청할 수 있습니다.

1. **반복적 접근**: 처음 생성된 이미지가 완벽하지 않을 수 있습니다. 이를 출발점으로 삼아 프롬프트를 반복적으로 수정하며 원하는 결과에 가까워지세요.

1. **화면비율 및 구성**: 이미지의 화면비율이나 구성을 선호한다면 프롬프트에 포함하세요. 예를 들어, 가로형 이미지를 요청하거나 피사체를 한쪽으로 배치하도록 요청할 수 있습니다.

1. **문화적 및 맥락적 참조**: 적절하다면, 추가적인 맥락을 제공할 수 있는 문화적 또는 역사적 참조를 포함하세요.

1. **책임 있는 AI 고려사항**: 프롬프트가 책임 있는 AI 사용 원칙을 준수하도록 유의하세요. 공격적이거나 고정관념을 강화하거나 저작권을 침해하는 이미지를 생성하지 마세요.

1. **테스트와 학습**: 다양한 프롬프트를 실험하며 DALL-E 3가 다양한 설명을 어떻게 해석하는지 이해하세요. 이를 통해 시간이 지나며 프롬프트의 정확성을 개선할 수 있습니다.

1. **가이드라인 준수**: OpenAI의 사용 사례 정책 및 콘텐츠 가이드를 따르세요. OpenAI의 콘텐츠 정책에 따라 허용되지 않는 이미지를 요청하지 마세요.

## 브랜드 마스코트 생성

이번 워크숍에서는 DALL-E 3의 기능을 활용하여 브랜드 마스코트를 생성해 보겠습니다. 여기에는 친근한 동물, 로봇, 추상적 인물 등 다양한 테마가 포함됩니다.

또한 DALL-E 3의 다양한 매개변수를 테스트하며 생성된 이미지의 다양성을 탐구할 것입니다. 이러한 매개변수에는 다음이 포함됩니다:

- **이미지 크기**: 크기(예: 정사각형, 가로형, 세로형)를 변경해 보고, 마스코트 디자인과 캠페인 활용성에 미치는 영향을 확인합니다.
- **이미지 스타일**: 자연스럽거나 생생한 스타일 등 다양한 스타일을 실험해 보고, 브랜드 성격에 가장 잘 맞는 스타일을 찾아보세요.
- **이미지 품질**: 고해상도 이미지를 생성해 인쇄용으로 사용하거나, 웹 또는 소셜 미디어용 저해상도 버전을 생성합니다. 크기는 HD 또는 표준으로 설정할 수 있습니다.

1. 브랜드 마스코트를 생성해 봅시다. 다음과 같은 프롬프트를 고려하세요:

```A friendly robot mascot with a smiling face, designed in a cartoon style.```

![친근한 로봇 마스코트](../../../../lab/Skillable Workshop Instructions/Images/robot-mascot-friendly.png)

```A playful fox mascot with a colorful scarf, representing agility and creativity.```

```An abstract figure with geometric shapes, conveying innovation and technology.```

2. Playground에서 _점 세 개 아이콘_을 클릭한 후, 설정으로 이동합니다.
3. 각 섹션에서 _드롭다운 화살표_를 클릭해 매개변수를 변경합니다.
4. 업데이트된 설정으로 프롬프트를 다시 시도해 보세요.

## 고급 프롬프트 작성

이제 기본 프롬프트를 살펴봤으니, 새로운 것을 시도해 봅시다.

>[!alert] 시스템 메시지가 비어 있는지 확인하세요. 필요하면 **Reset to Default**를 클릭하여 기본값으로 재설정할 수 있습니다.

이제 gpt-4o-mini가 생성한 프롬프트를 기반으로 이미지를 생성해 보겠습니다.

1. **Chat Playground**로 돌아갑니다.

2. **System message**에서 **Give the model instructions and context** 옆에 있는 기존 메시지를 지워 시스템 메시지를 기본값으로 재설정합니다.

1. **채팅 상자**에 우리가 생성하고자 하는 제품의 상세 설명을 입력하고 모델에 요청을 제출합니다.

```
Generate a prompt for DALL-E 3 from this product description:

The 3D Animated Office Space Design by CreativeSpaces offers a modern, interactive representation of a professional work environment. This design concept includes ergonomic furniture, open and collaborative workspaces, greenery for a touch of nature, and large windows to maximize natural light. The layout also incorporates meeting pods, hot desks, and breakout areas for different work modes. The office has a neutral color palette, with accents of green and blue to create a calming yet productive atmosphere.

The 3D Animated Office Space Design is intended for use by architects, interior designers, and companies looking to revamp their workspaces. It highlights the importance of balancing privacy with collaboration, including quiet zones for focused work and shared areas for team interactions. The space features modern materials like glass and wood, combined with innovative lighting solutions to enhance productivity and employee well-being.

Beyond its aesthetic appeal, the 3D Animated Office Space Design is designed with functionality in mind. It includes ample storage solutions, acoustic panels to reduce noise, and modular furniture that can be rearranged to suit different needs. The green walls and potted plants throughout the office create a refreshing environment that promotes creativity and reduces stress. The design is presented in a high-quality 3D animation, providing a realistic walkthrough that allows clients to visualize the space effectively.
```

2. 응답을 받으면, 응답 상단의 점 세 개를 클릭하고 **Copy response to clipboard**를 선택합니다.

![복사 옵션](../../../../lab/Skillable Workshop Instructions/Images/ai-foundry-copy-response.png)

3. **Images Playground**로 돌아가 생성된 프롬프트를 사용해 이미지를 생성합니다.

4. Images Playground에서 **Deployments** 아래에 'dall-e-3'가 선택되어 있는지 확인한 뒤, **Prompt Box**에 생성된 프롬프트를 붙여넣습니다.

5. **Generate**를 클릭하고 얼마나 세부적인 이미지가 생성되는지 확인하세요.

![3D 작업 공간](../../../../lab/Skillable Workshop Instructions/Images/_Create%20a%203D%20animation%20of%20a%20modern%20office%20space%20design%20featuring%20ergonomic%20furniture,%20collaborative%20workspaces,%20and%20greenery%20elements.%20The%20office%20should%20have%20large%20windows%20for%20natural%20light,%20meeting%20pods,%20an.png)

## 다음 단계

축하합니다! 이제 실습의 두 번째 부분을 완료했으며, 다양한 이미지 에셋을 생성했습니다. 다음 실습에서는 모델을 활용해 멀티모달 요청을 처리하는 방법을 배웁니다.

**Next**를 클릭해 멀티모달 섹션으로 진행하세요.

**면책 조항**:  
이 문서는 기계 기반 AI 번역 서비스를 사용하여 번역되었습니다. 정확성을 위해 최선을 다하고 있지만, 자동 번역에는 오류나 부정확성이 포함될 수 있습니다. 원어로 작성된 원본 문서를 권위 있는 자료로 간주해야 합니다. 중요한 정보의 경우, 전문적인 인간 번역을 권장합니다. 이 번역 사용으로 인해 발생하는 오해나 잘못된 해석에 대해 당사는 책임을 지지 않습니다.  