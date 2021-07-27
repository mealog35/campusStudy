# Part 19. 속성-플랙스

### 플랙스
  - container : Items를 감싸는 부모 요소이며, 각 Item을 정렬하기 위해선 container가 필수입니다
    - display, flex-flow, justify-content, align-items
  - Items: order, flex, align-self 속성을 사용할 수 있습니다

### flex container
  - display : flex container를 정의 (블록/인라인)
    - flex : 블럭요소처럼 사용이 되고 위에서부터 아래로 쌓이게 됨
    - inline-flex : 인라인이다 보니 수평으로 쌓이게 됨
    
### flex-flow
  - flex Items의 주 축을 설정하고 Items의 여러 줄 묶음도 설정합니다
    - flex-direction : items의 주 축을 설정 // row(수평정렬) <-> row-reverse  column(수직정렬) <-> column-reverse
    - flex-wrap : items의 여러 줄 묶음 설정
      - nowrap : 기본값 여러줄로 묶지 않고 한줄로 표시
      - wrap : Items를 여러 줄로 묶음
      - wrap-reverse : 묶되 역 방향으로 묵음

### flex 주축과 교차축, 시작점과 끝점
  - 주 축(main-axis) : row Or column 어느 방향으로 하는지
  - 교차 축(cross-axis) : 그것과 교차가 되도록 하는 것
  - 시작점(flex-start) : 주축이나 교차 축의 시작하는 지점
  - 끝점(flex-end) : 주축이나 교차 축의 끝나는 지점

### justify-content
  - 주 축의 정렬 방법을 설정합니다
    - flex-start : items를 시작점으로 정렬
    - flex-end: items 끝점으로 정렬
    - center : items를 가운데 정렬
    - space-between : 시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨
    - space-around : items를 균등한 여백을 포함하여 정렬

### align-content
  - 교차 축의 정렬 방법을 설정합니다
  - items가 여러 줄(2줄 이상)이고 여백이 있을 경우만 사용할 수 있습니다
    - stretch : container의 교차 축을 채우기 위해 Items를 늘림
    - flex-start : items를 시작점으로 정렬
    - flex-end: items 끝점으로 정렬
    - center : items를 가운데 정렬
    - space-between : 시작 Item은 시작점에, 마지막 Item은 긑점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨
    - space-around : items를 균등한 여백을 포함하여 정렬

### align-items
  - 교차 축에서 items의 정렬 방법을 설정합니다
  - 여러 줄일 경우에는 align-content 속성이 우선됩니다
    - stretch : container의 교차 축을 채우기 위해 Items를 늘림
    - flex-start : items를 시작점으로 정렬
    - flex-end: items 끝점으로 정렬
    - center : items를 가운데 정렬
    - baseline : 문자를 기준으로 정렬이 됨

### Flex Items
  - order : flex item의 순서를 설정 / 숫자가 크면 뒤로 밀림 음수일수록 앞으로 가게 됨
  - flex-grow : item의 증가 너비 비율을 설정합니다 숫자가 크면 더 많은 너비를 가집니다

### flex-shrink
  - item이 감소하는 너비의 비율을 설정 , 숫자가 크면 더 많은 너비가 감소함

### flex-basis
  - item의 기본 너비를 설정

### flex(0,1,0)
  - 너비를 설정하는 단축 속성
  
### align-self
  - 교차 축에서 개별 item의 정렬 방법을 설정
  - align-items보다 더 우선으로 적용이 됨
  - auto가 추가로 있음(align-items)에서 속성을 상속받음
