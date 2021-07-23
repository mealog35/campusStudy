# Part 11. CSS 개요, 선택자, 상속

### 문법
  - 선택자의 역할 : 속성과 값을 지정할 대상을 검색
```react
  <div>hello</div>
  div{
  color:red
 } 
```
  - 속성과 값의 역할 : 검색된 대상에 지정될 CSS 명령
  - comment : 주석으로 수정사항이나 설명들을 작성함

### 선언방식
  - 인라인 방식: 속성 안에다가 스타일을 넣음
  - 내장 방식 : style 안에 스타일을 넣음
  - 링크 방식 : 외부 문서로 CSS 불러와서 스타일을 넣음
  - @import 방식 : 외부 문서로 CSS를 불러와 적용함 (css가 css를 불러옴)

### 기본 선택자
  - 전체 선택자 : 모든 요소를 선택(*)
  - 태그 선택자 : 태그 이름으로 요소 선택 ( div, img, span, table, h1, h3 ...)
  - 클래스 선택자 : class 속성의 값인 요소 선택 (.e)
  - 아이디 선택자 : id 속성의 값인 요소 선택 (#e)

### 복합 선택자
  - 일치 선택자 : ex)span.orange -> 태그 + 클래스
  - 자식 선택자 : ex)ul > .orange -> 태그 + li(클래스)
  - 후손(하위) 선택자 : ex) div span -> 부모요소 + 자식요소
  - 인접 형제 선택자 : ex) .orange + li -> li(클래스) + 바로 다음 형제만 선택자
  - 일반 형제 선택자 : ex) .orange - li -> li(클래스) + 바로 다음 형제들 모두 선택

### 가상클래스 선택자(:)
  - hover : 마우스가 올라가 있는 동안에만 선택
  - active : 마우스로 클릭하는 동안에만 선택
  - focus : 포커스 된 동안에만 선택 / input 에서만 사용할 수 있음 / 탭 키를 눌러서 사용함
  - first child : 형제 요소 중 첫번째 요소라면 선택 ex) .fruits li:first-child
  - last child : 형제 요소 중 마지막 요소를 선택 ex) .fruits li:last-child
  - nth child : 형제 요소 중 n 번째 요소라면 선택 / n 이 1부터 시작함
  - 오류가 뜨는 예시 ) 만약 정확하게 확인을 할려면 뒤에서 부터 확인을 하는게 더 정확함
    - 자식요소중에 첫번째 <div>딸기</div> 인데 p 가 선택되었기 때문에 오류가 남 
```react
  .fruits p:nth-child(1){
    color:red;
  }
  <div class="fruits">
    <div>딸기</div>
    <p>사과</p> // 실제로 선택되지 않음
    <p>망고</p>
    <span>오렌지</span>
  </div>  
```

```react
.fruits :first-child {
  color: red;
}

  <div class="fruits">
      <div>딸기</div>
      <div>딸기</div>
      <div>
          <div>1</div>
          <div>1</div>
          <div>1</div>
      </div>
    </div> 
```
  -nth of type : 자식요소중에 태그에서 n 번째를 찾을 수 있음
```react
  .fruits p:nth-of-type(1){
    color:red;
  }
  <div class="fruits">
    <div>딸기</div>
    <p>사과</p> // 선택됨
    <p>망고</p>
    <span>오렌지</span>
  </div>  
```
```react
  .fruits .red:nth-of-type(1){ //<li>딸기</li> 이거를 의미하는데 .red로 되어있어서 오류가 발생했음 
    color:red;
  }
  
  <ul class="fruits">
    <li>딸기</li>
    <li class="red">사과</li> // 선택되지 않음 : 자식요소로 같은 li로 되어있기 때문에 인식을 하지 못함
    <li>망고</li>
    <li class="red">오렌지</li>
  </ul>  
```
  - 부정선택자 : s가 아닌 e 선택
```react
  .fruits li:not(.strawberry){ 
    color:red;
  }
  
  <ul class="fruits">
    <li>딸기</li>
    <li class="strawberry">딸기</li> 
    <li>망고</li>
    <li>오렌지</li>
  </ul>
```

### 가상 요소 선택자 (::before)
  - 요소 내부의 앞에, 내용을 삽입
```react
  li::before{
    content:"숫자"; // 무조건 있어야 함
    width:30px;
    height:30px;
    margin-right:20px;
```

### 가상 요소 선택자 (::after)
  - 내부 뒤의 요소에 삽입
```react
  li::after{
    content:".0"; // 무조건 있어야 함
    width:30px;
    height:30px;
    margin-right:20px;
```

### 속성 선택자
```react
  <input type="text" value="lee">
  <input type="password" value="1234">
  <input type="text value="disabled text" disabled>
  [attr(속성)] -> 값을 넣어줘서 스타일을 줌
  [disabled]{
    opacity:0.5;
    color:red;
  }  
  
  [attr=value]
  [type=password]
```

```react
  <button class="btn-success>success</button>
  <button class="btn-danger">danger</button>
  <button>Normal</button>
  
  <!--btn- 로 시작하는 클래스에는 다 스타일을 주게 됨-->
  [class^="btn-]{
    font-weight:bold;
    border-radius:20px;
  }
  <!-- 끝에 있는 클래스로 구별해서 스타일을 주게 됨-->
  [class$="success"]{
    color:green;
  }
  <!-- 끝에 있는 클래스로 구별해서 스타일을 주게 됨-->
  [class$="danger"]{
    color:red;
  }
```

### 우선순위 결정
  - 같은 요소가 여러 선언의 대상이 될 경우, 어떤 선언의 CSS 속성을 우선 적용할지 결정하는 방법
    - 가장중요(!important)
    - 인라인선언방식
    - 아이디선택자
    - 클래스선택자
    - 태그선택자 / 요소
    - 전체선택자
    - 상속
