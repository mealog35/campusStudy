# Part 03. HTML & CSS

### 기본 문법과 선택자의 역할
```react
div{
  font-size:20px;
  color:red;
 }
 선택자{
  속성:값;
  속성:값;
 }
 ```
 ### 속성(properties)과 값(value)
```react
div {
  color: red; /* 글자색은 빨강 */
  font-size: 20px; /* 글자 크기는 20px */
  width: 300px; /* 가로 너비는 300px */
  margin: 20px; /* 바깥 여백은 20px */
  padding: 10px 20px; /* 안쪽 여백은 위아래 10px, 좌우 20px */
  position: absolute; /* 위치는 부모 요소 */
}
```
 ### 선언방식
  - 태그에 직접 작성하기(인라인)
```react
  <div style="color: red;">태그에 직접 작성1</div> <!-- red -->
```
  - HTML에 포함하기(내장)
```react
 <style>
    div {
      color: red;
    }
  </style>  
  <body>
  <div>HTML에 포함1</div> <!-- red -->
  <div>HTML에 포함2</div> <!-- red -->
  <div>HTML에 포함3</div> <!-- red -->
</body>
```
  - 외부에서 불러오기
```react
  <head>
  <link rel="stylesheet" href="/css/main.css">
  </head>
  <body>
    <div>HTML에 외부에서 불러오기1</div> <!-- red -->
  </body>
  
  <!--외부스타일 시트-->
  div {
  color: red;
  }
```
### 선택자
  - 특정한 HTML 요소에 css를 주기 위함
  - 클래스로 찾기

### 속성
  - #width(가로 너비)
  - #height(세로 너비)
  - #font-size(글자 크기/기본값은 16px)
  - #margin(요소의 바깥 여백)
  - #padding(요소의 안쪽 여백)
  - #color(글자 색상)
  - #background(요소 색상)
