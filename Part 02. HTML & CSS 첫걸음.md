# Part 02. HTML & CSS 첫걸음

### 기본 형태
  - 태그는 각자의 의미를 가지고 있음
  - 태그와 요소는 조금씩 다름
``` react 
<TAG>(element)</TAG>
```
### 속성과 값
  - 태그의 기능을 확장하기 위해 '속성'을 사용함 
``` react 
<TAG 속성="값">(element)</TAG>
<img src="./my_photo,jpg>
<div class="name">hong gil dong</div>
```
### 부모와 자식 요소
```react
<PARENT>
  <CHILD></CHILD>
</PARENT>
```
### 빈 태그
  - HTML에는 닫히는 개념이 없는 태그들이 있음
  - XHTML 버전에서는 / 사용하고, /를 사용하면 통일성있게 하는게 좋음
```react
<!-- `/`가 없는 빈 태그 -->
<TAG>

<!-- `/`가 있는 빈 태그 -->
<TAG/>
<TAG />
```

### DOCTYPE(DTD)
  - 마크업 언어에서 문서 형식을 정의함
  - meta 정보를 나타냄
  - HTML은 크게 1,2,3,4,X-,5버전이 있음

### HEAD 태그(TITLE, META, LINK, STYLE, SCRIPT)
  - TITLE(웹 페이지의 제목)
  - META(웹 페이지의 정보)
  - LINK(CSS 불러오기)
  - STYLE(CSS 직접적으로 작성하기)
  - SCRIPT(JS 불러오거나 작성하기)

### BODY 태그 (div, image) 웹 표준 검사
  - div(막 쓰는 태그/분할하기도 함)
  - img(이미지를 삽입할 때 사용)

### 예제
  - 웹 페이지 제작하기
