# Part 1 - 텍스트 생성

이 워크숍의 첫 번째 파트에 오신 것을 환영합니다. 여기에서는 gpt-4o-mini 모델과 상호작용하여 텍스트를 생성하는 방법을 배워보겠습니다.

> [!TIP]  
> **프롬프트 엔지니어링이란?**  
> 프롬프트 엔지니어링은 자연어 처리(NLP)에서 중요한 개념으로, **작업에 대한 설명을 입력에 포함시켜** 모델이 **원하는 결과**를 출력하도록 **유도하는 방법**을 의미합니다.

## 기본 프롬프트 작성

몇 가지 프롬프트를 작성하고, 채팅 플레이그라운드를 사용하여 응답을 관찰해 보겠습니다. 채팅 플레이그라운드를 사용하려면 다음 단계를 따르세요:

![채팅 인터페이스를 보여주는 이미지](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-basicprompting.jpeg)

1. 왼쪽 탐색 메뉴에서 **Playgrounds** 섹션으로 이동한 후, **Try the Chat Playground**를 클릭합니다.  
2. 채팅 플레이그라운드에서 _"Type user query here."_ 라는 텍스트 상자를 찾습니다.  
3. 아래 제공된 프롬프트 예제에서 "T" (예: ``here is a sample prompt``)를 클릭하면 해당 프롬프트가 현재 커서 위치에 자동으로 입력됩니다.  
4. 프롬프트를 추가한 후, 입력 상자 옆에 위치한 종이비행기 아이콘을 찾아 클릭합니다. 이 아이콘을 클릭하면 텍스트가 모델 배포에 제출됩니다.  
5. 쿼리를 전송한 후, 모델이 처리하고 응답을 생성할 때까지 잠시 기다리세요. 응답은 입력 아래의 채팅 창에 표시됩니다.  

아래 몇 가지 예제를 시도해 보세요. 자신만의 프롬프트를 창의적으로 작성해 결과를 확인하는 것도 추천합니다!

### 웹사이트 카피와 대화 기록

```
Suggest a tagline for the website landing page of an ice cream shop called SweetScoops Delight.
```

채팅 기록을 지우지 않고 다음 프롬프트를 시도해 보세요:

```
Generate website copy for the homepage of the ice cream shop.
```

모델이 *SweetScoops Delight* 웹사이트를 위한 카피를 제공하고 있는 것을 알 수 있습니다. 우리가 다시 회사 이름이나 비즈니스를 명시하지 않았음에도 불구하고 말이죠. 이는 모델이 **전체 대화 기록**을 컨텍스트로 사용하고, 최신 프롬프트만 참조하지 않기 때문입니다.  
AI 모델은 사용자가 떠났다가 돌아오면 이전 상호작용을 학습하거나 기억할 수 없습니다. 하지만 애플리케이션이 프롬프트 엔지니어링을 사용해 '기억'을 추가적으로 제공하고 있는 것입니다.

> [!NOTE]  
> 컨텍스트 윈도우 크기를 제어할 수 있습니다. 이는 모델이 컨텍스트로 고려할 이전 상호작용의 개수를 나타냅니다(기본값은 10). **Parameters** 섹션에서 설정을 변경할 수 있습니다.

모델 매개변수를 다음과 같이 제어할 수 있습니다:

![매개변수 탭을 보여주는 이미지](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-parameters.jpeg)

1. 채팅 인터페이스에서 **Parameters** 섹션으로 이동합니다.  
2. Parameters 섹션에 들어가면 설정 컨트롤을 조정할 수 있습니다. 모델이 컨텍스트로 고려할 과거 메시지의 개수를 변경할 수 있습니다. 설정이 완료되면 변경 사항이 자동으로 적용됩니다.

### 요약 및 주요 엔터티 추출

이전 단계에서 생성된 카피는 시작하기에 좋은 자료이지만, 랜딩 페이지에는 너무 길 수 있습니다. 더 짧은 버전을 만들어 보겠습니다.

텍스트 요약은 대규모 언어 모델(LLM)의 잘 알려진 기능입니다. 이는 긴 텍스트를 짧게 요약하는 데 사용됩니다.

> [!TIP]  
> 요약하려면 프롬프트에 "tl;dr" (too long; didn’t read)를 추가하고 요약할 텍스트를 입력하면 됩니다.

또한, LLM에게 텍스트에서 주요 정보를 추출하도록 지시할 수도 있습니다. 이 경우, **SEO 최적화**를 위한 키워드를 얻는 데 유용합니다. 아래 프롬프트를 사용해 이전 카피를 요약하고 유용한 데이터를 추출해 보세요.

```
1. tl;dr
2. Extract company name, categories of products and business unique values from the long description above.
```

## 고급 프롬프트 작성

>[!alert] 다음 섹션으로 넘어가기 전에 **Clear Chat** 버튼을 클릭해 메시지 기록을 초기화하세요. 이를 위해 오른쪽 상단에 있는 **빗자루 모양 아이콘**을 클릭합니다. 팝업이 나타나면 **Clear** 버튼을 눌러 채팅 기록을 삭제하세요.

![채팅 기록 삭제 버튼 스크린샷](../../../../lab/Skillable Workshop Instructions/Images/text-generation-clearchat.jpg)

### 제로샷 학습

LLM은 방대한 양의 데이터를 학습했기 때문에, 최소한의 프롬프트로도 일부 작업을 수행할 수 있습니다. 이를 **제로샷 학습**이라고 합니다. 예를 들어, 모델에게 제품 이름 목록을 생성하고 이를 분류하도록 요청해 보겠습니다:

```
Generate 10 unique menu items for a futuristic themed restaurant, including dish names and a short description.
```  
>[!alert] 다음 섹션으로 넘어가기 전에 **Clear Chat** 버튼을 클릭해 메시지 기록을 초기화하세요.

### 퓨샷 학습

제로샷 학습이 복잡한 작업에서 원하는 결과를 제공하지 못할 경우, **퓨샷 프롬프트**를 통해 예제를 제공하여 모델이 원하는 방향으로 결과를 생성하도록 유도할 수 있습니다. 예제는 모델이 어떻게 작동해야 하는지 명확히 보여줍니다. 다음은 제품을 분류하기 위한 퓨샷 학습 프롬프트의 예입니다.

```
Generate 10 unique pizza menu items with futuristic names, including the name of the pizza and a short description.

Examples:  
The Nebula Supreme: A classic supreme pizza with pepperoni, sausage, bell peppers, onions, and olives, topped with a hint of spicy marinara sauce.
Galactic Garden: A vegetarian delight featuring spinach, cherry tomatoes, mushrooms, and artichokes with a basil pesto drizzle.
Asteroid Meat Feast: Loaded with pepperoni, ham, ground beef, bacon, and Italian sausage for a hearty, protein-packed slice.
```

### 연쇄 사고 프롬프트

>[!alert] 시작하기 전에, **Clear Chat**를 클릭하여 이전 상호작용의 컨텍스트를 제거하세요.

LLM과 상호작용할 때 유용한 팁은, 마치 훈련받지 않은 인턴과 대화한다고 상상하는 것입니다. 작업에 대한 세부 정보를 많이 제공할수록 더 나은 결과를 얻을 수 있습니다. 특히, 작업을 더 작은 단계로 나누고 각 단계에 대해 프롬프트를 제공하는 전략이 유용합니다. 웹사이트 카피 생성 작업에서 이를 시도해 보겠습니다.

```
Develop a new pizza for our restaurant.

Instructions:
- Start by deciding on a theme for the new pizza.
- Determine the overall flavor profile. Should it be spicy, sweet, savory, or a mix?
- Pick the base ingredients. This includes the type of sauce and cheese
- Think about unique toppings that fit the theme and flavor profile.
- Finally, come up with a creative, memorable name that fits both the futuristic theme of the restaurant and the flavor experience you’ve crafted.
```

또 다른 방법은 **연쇄 사고**라는 기술을 사용하는 것입니다. 여기서 LLM은 작업을 더 작은 단계로 나누고, 세계에 대한 지식과 추론 능력을 활용하여 작업 해결로 이어지는 사고 과정을 생성합니다. 채팅 기록을 다시 초기화한 후, 아래 사용자 프롬프트를 입력하여 '연쇄 사고 프롬프트'를 확인해 보세요:

```
Develop a new pizza for our restaurant.

Take a step-by-step approach in your response: Start by thinking about the theme, considering how it fits into the restaurant's overall futuristic concept. Then, define the flavor profile, keeping in mind our audience's preferences and the overall taste experience you want to create. Next, choose the base ingredients, including the sauce type and cheese blend, and think about unique toppings that make this pizza stand out. Finally, decide on a name that aligns with the theme and enhances the pizza's appeal. Include your reasoning before sharing the final answer in the below format: ANSWER is: <pizza description>.
```

## 시스템 메시지와 추가 정보

>[!alert] 다음 섹션으로 넘어가기 전에 **Clear Chat** 버튼을 클릭해 메시지 기록을 초기화하세요.

### 시스템 메시지

> [!TIP]  
> **시스템 메시지란?**  
> 시스템 메시지는 대화 시작 시 모델에 지침이나 컨텍스트를 전달하는 데 사용됩니다. 사용자 메시지와는 다른 형식으로 표시되며, 모델이 대화에서 자신의 역할을 이해하는 데 도움을 줍니다. 시스템 메시지는 일반적으로 모델의 동작을 안내하거나 톤을 설정하거나 원하는 출력을 지정합니다. 이를 효과적으로 활용하면 모델이 더 정확하고 관련성 높은 응답을 생성하도록 유도할 수 있습니다.

![시스템 메시지 탭을 보여주는 이미지](../../../../lab/Skillable Workshop Instructions/Images/aifoundry-chat-instructions.jpeg)

시스템 메시지를 업데이트하여 모델에 지침과 컨텍스트를 제공하려면 다음 단계를 따르세요:

1. 채팅 인터페이스에서 **System message** 섹션으로 이동합니다.  
2. System message 섹션에서 기존 메시지를 지우세요. System message 필드 안을 클릭하여 커서를 놓고 아래 텍스트를 삽입합니다:

```
## Task
You are a menu designer for a futuristic-themed pizzeria restaurant named "Galactic Slice". Your goal is to generate creative menu items and descriptions. Keep your answers brief, engaging, and aligned with the restaurant's theme.

Your answer should be brief and engaging. Always use a friendly and professional tone of voice.

## Safety
Keep the descriptions family-friendly and suitable for all age groups visiting our pizzeria. Avoid any irrelevant information and controversial opinions.
```

3. **Apply changes** 버튼을 찾습니다. 이는 System message 상자 바로 아래에 있습니다. 이 버튼을 클릭해 변경 사항을 저장하고 적용하세요.  
4. 변경 사항을 적용한 후, 팝업에서 **Continue** 버튼을 클릭하여 시스템 메시지를 업데이트하세요.

우리는 모델에 **명확한 작업**, **톤**, **안전 조치**를 제공했습니다. 모델은 비즈니스에 사용되는 기술의 일부로서 브랜드와 동일한 접근 방식과 윤리를 가져야 합니다. 시스템 메시지에 톤을 설정하는 세그먼트를 추가하면 사용 사례에 맞는 응답 유형을 설정하는 데 도움이 됩니다.

시스템 메시지에 제공된 텍스트는 모델에 의해 특별히 처리되며, 사용자 메시지나 다른 컨텍스트보다 모델의 응답에 더 큰 영향을 미치도록 설계되었습니다. 또한, 채팅 기록을 초기화해도 모든 상호작용에서 유지됩니다.

5. 추가된 컨텍스트로 모델의 동작이 어떻게 변화하는지 확인하려면 아래 텍스트 상자에 다음 프롬프트를 입력해 보세요:

```
Write a brief description of the restaurant, including the categories of menu items offered.
```

모델이 요청된 정보를 제공할 뿐만 아니라, 식당 테마와 이름을 고수하는 등 정확히 지침을 따르는 것을 볼 수 있습니다. 더 나아가 **안전 조치**를 테스트할 수도 있습니다:

```
What are your thoughts on the just concluded election?
```

6. 모델은 (회사의 주제와 무관하며 논란이 될 수 있는) 이 질문에 답변하지 않고, 회사와 제품의 주제에만 집중합니다.

### 근거 기반 프롬프트

>[!alert] 이 섹션으로 넘어가기 전에 **Clear Chat**를 클릭하여 채팅 기록을 초기화하세요.

지금까지 모델은 창의적으로 비즈니스 가치 제안과 제품(메뉴) 제공을 발명했습니다. 그러나 실제 시나리오에서는 모델이 현실에 기반한 텍스트를 생성하고 실제 비즈니스를 반영하기를 원합니다. 이를 위해 **Retrieval Augmented Generation (RAG)**이라는 기술을 사용할 수 있습니다. 이 기술은 모델에 비즈니스에 대한 사실이나 정보를 제공하여 더 정확하고 관련성 높은 텍스트를 생성하도록 돕습니다.

> [!NOTE]  
> **Retrieval-Augmented Generation (RAG)**은 언어 모델과 검색 시스템을 결합하여 더 정확하고 상세한 정보를 제공하는 AI 기술입니다. RAG 패턴에서는 시스템이 일반적으로 데이터베이스에서 관련 정보를 검색한 후 이를 활용해 더 정보에 기반한 텍스트 응답을 생성합니다. 이 실습에서는 모델에 비즈니스 정보를 프롬프트로 제공하여 검색 프로세스를 시뮬레이션합니다.

다음으로 Contoso Outdoor Company의 제품 카탈로그를 기반으로 한 카피를 생성하는 시나리오를 살펴보겠습니다. 추가된 제품 정보를 시스템 메시지에 제공할 수 있습니다. 아래 정보를 기존 시스템 프롬프트 끝에 삽입한 후 **Apply changes**를 클릭하세요.

```
## Business Information
Contoso Outdoor Company is an e-commerce business that specializes in outdoor clothing and equipment. The company offers a wide range of products, including tents, backpacks, hiking clothing, and sleeping bags. The company's main value proposition is to provide high-quality outdoor gear for every level of outdoor enthusiast at affordable prices.

Products offered:
1. Tents: 
    - TrailMaster X4 Tent: Crafted from durable polyester, this tent boasts a spacious interior perfect for four occupants. It ensures your dryness under drizzly skies thanks to its water-resistant construction, and the accompanying rainfly adds an extra layer of weather protection.
    - Alpine Explorer Tent: This robust, 8-person, 3-season marvel is from the responsible hands of the AlpineGear brand. Promising an enviable setup that is as straightforward as counting sheep, your camping experience is transformed into a breezy pastime.
    - SkyView 2-Person Tent: This tent offers a spacious interior that houses two people comfortably, with room to spare. Crafted from durable waterproof materials to shield you from the elements, it is the fortress you need in the wild. 

2. Backpacks:
    - Adventurer Pro Backpack: Uniquely designed with ergonomic comfort in mind, this backpack ensures a steadfast journey no matter the mileage. It boasts a generous 40L capacity wrapped up in durable nylon fabric ensuring its long-lasting performance on even the most rugged pursuits. 
    - SummitClimber Backpack: your reliable partner for every exhilarating journey. With a generous 60-liter capacity and multiple compartments and pockets, packing is a breeze. Every feature points to comfort and convenience; the ergonomic design and adjustable hip belt ensure a pleasantly personalized fit, while padded shoulder straps protect you from the burden of carrying. 
    - TrailLite Daypack: Built for comfort and efficiency, this lightweight and durable backpack offers a spacious main compartment, multiple pockets, and organization-friendly features all in one sleek package. 

3. Hiking Clothing:
    - Summit Breeze Jacket: This lightweight jacket is your perfect companion for outdoor adventures. Sporting a trail-ready, windproof design and a water-resistant fabric, it's ready to withstand any weather. 
    - TrailBlaze Hiking Pants: Crafted from high-quality nylon fabric, these dapper troopers are lightweight and fast-drying, with a water-resistant armor that laughs off light rain. Their breathable design whisks away sweat while their articulated knees grant you the flexibility of a mountain goat.
    - RainGuard Hiking Jacket: the ultimate solution for weatherproof comfort during your outdoor undertakings! Designed with waterproof, breathable fabric, this jacket promises an outdoor experience that's as dry as it is comfortable.
```

추가된 컨텍스트로 모델의 동작이 어떻게 변화하는지 확인하려면 아래 프롬프트를 입력해 보세요:

```
Write a short description for each of the following product categories: tents, backpacks, hiking clothing.
```

## 다음 단계

축하합니다! 첫 번째 실습을 완료하셨습니다. 이제 프롬프트 엔지니어링을 사용해 언어 모델로 텍스트를 생성하는 방법을 배웠습니다. 다음 실습에서는 모델을 사용해 이미지 자산을 생성하는 방법을 배워보겠습니다.

**Next**를 클릭하여 이미지 섹션으로 이동하세요.  

**면책 조항**:  
이 문서는 기계 기반 AI 번역 서비스를 사용하여 번역되었습니다. 정확성을 위해 노력하고 있지만, 자동 번역에는 오류나 부정확성이 포함될 수 있음을 유의하시기 바랍니다. 원본 문서의 원어 버전이 권위 있는 출처로 간주되어야 합니다. 중요한 정보의 경우, 전문 인간 번역을 권장합니다. 이 번역 사용으로 인해 발생하는 오해나 잘못된 해석에 대해 당사는 책임을 지지 않습니다.