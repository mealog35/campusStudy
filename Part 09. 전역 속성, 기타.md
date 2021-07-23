# Part 09. 전역 속성, 기타

### class 와 id
  - class: 별칭으로 지정
  - id : 문서에서 고유한 식별자를 정의

### style
  - 요소에 적용할 CSS 선언

### title
  - 요소의 정보(설명)을 지정

### lang
  - 요소의 언어를 지정

### data-*
  - 사용자 정의 데이터 속성을 지정
  - 카멜표기법을 이용함

### draggable
  - 요소가 drag and drop api를 사용 가능한지 여부를 지정

### hidden
  - 요소를 숨길때 사용함

### tabindex
  - 탭 키를 이용해 요소를 순차적으로 포커스 탐색할 순서를 지정
  - 0 이라는 값을 넣어줘서 할 수 있음
  - -1 은 제외 됨
```react
    <input type="text" value="1">
    <input type="text" value="2">
    <input type="text" value="3">
    <div tabindex="0">2.5</div>
    <input type="text" value="4">
    <input type="text" value="5">
    <input type="text" value="6">
    <input type="text" value="7" tabindex="-1">
```

### 절대 경로와 상대 경로
  - ./ : 주변에서 찾는다
  - 상대경로 : ./ ../
  - 절대경로: http , /(앞에 도메인 주소가 생략되어 있음)

### 주석
  - ctrl + / (window 경우)
  - comman + / (mac 경우)
  
### 특수기호
  - &nbsp : 공백을 나타내는 특수기호
  - &lt < &gt >
