# Part 04. 개요, 요소 - 주요범위 & 메타데이터

### HTML - 블럭 레벨(block level) 요소와 인라인(inline)요소
  - 1.블럭요소
    - 1.DIV H1 P
    - 2.사용가능한 최대 가로 너비를 사용한다
    - 3.크기를 지정할 수 있다
    - 4.(width:100%; height:0;로 시작)
    - 5.수직으로 쌓임
    - 6.margin, padding 위 아래 좌 우 사용 가능하다
    - 7.레이아웃
  - 2.인라인요소
    - 1.SPAN IMG
    - 2.필요한 만큼의 너비를 사용한다
    - 3.크기를 지정할 수 없다
    - 4.(width:0;height:0;로 시작)
    - 5.수평으로 쌓임
    - 6.위 아래는 사용할 수 없다
    - 7.text

### 주요범위 & 메타데이터(html,head,body,title)

```react
  <head>
    <문서의 정보>
    -기타 정보
    <meta charset="UTF-8>
    <title>lalala</title>
    -스타일 직접 입력
    -스타일 외부에서 가져와서 연결
  </head>
  <body>
    문서의 구조
