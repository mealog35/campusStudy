# Part 08. 표 콘텐츠 & 양식

### TABLE
  - 데이터 표
  - th : 머리글 칸을 지정함
    - colspan : 확장하려는 열의 수
    - rowspan : 확장하려는 행의 수
    - scope : 자신이 누구의 머리글 칸인지 명시
    - headers : id 값을 가지고 와서 어디 소속인지를 구분 시켜줌
  - td : 일반 칸을 지정

### caption
  - 표의 제목을 설정
  - 테이블당 하나의 caption만 사용가능함
  - col : 한 열에 배경색을 다 줄 수가 있음 / span : 연속되는 열 수

### THEAD, TBODY, TFOOT (화면에 출력되지는 않음)
  - THEAD : 테이블의 머릿글을 표시함 
  - TBODY : 테이블의 바디를 나타냄
  - TFOOT : 테이블의 마지막 부분을 나타냄

### form
  - 웹 서버에 정보를 제출하기 위한 양식 범위를 정의
  - GET 방식 : password 가 URL 링크에 다 보여줌
  - POST 방식 : password가 URL에 보이지 않도록 함
  - autocomplete : 자동완성 기능을 끄거나 킬수 있음
  - novalidate : 유효성 검사를 하지않겠다는 것을 의미함

### input
  - 사용자에게 입력 받을 데이터 양식
  - type: 어떤 데이터를 입력받을 지를 표시해줘야 함
  - name : URL에 id 값, password 값 이 나올 수 있도록 함(GET 방식일 경우)

### label
  - 라벨 가능 요소의 제목
  - for :참조할 라벨 가능 요소의 id 속성 값

### button
  - 선택 가능한 버튼을 지정
  - disabled 버튼을 비활성화 함
  - onclick : 자바스크립트 함수를 호출할 수 있음

### TEXTAREA
  - 여러 줄의 일반 텍스트 양식
  - rows : 양식의 줄 수

### FIELDSET LEGEND
  - 같은 목적의 양식을 그룹화 하여 제목을 지정
  - radio : 택1만 가능함
  - FIELDSET : 그룹화 함
  - LEGEND : 그릅화 된 거에 타이틀을 의미함

### SELECT, DATALIST, OPTGROUP, OPTION
  - select: 옵션을 선택하는 메뉴
    - autocomplete : 자동 완성 기능을 사용할 것인지 여부
    - disabled : 선택 메뉴를 비활성화
    - form : 선택 메뉴가 속할 하나 이상의 form 의 id 속성
  - optgruop : option을 그룹화
  - option : 선택 메뉴나 자동완성에서 사용될 옵션
  - datalist : input 태그에 미리 정의된 옵션 자동완성 기능을 제공하는 데 사용

```react
<input type="text" list="fruits">
<datalist id="fruits">
  <option>Apple</option>
  <option>Orange</option>
  <option>Manggo</option>
</datalist>  
```
### Progress
  - 작업의 완료 진행률을 표시 (로딩바)
  
