# Part 13. 박스 모델

### width , height
  - 요소의 가로,세로 너비를 지정
  - 기본 auto로 설정이 되어있음 다만, 인라인 요소(텍스트다룰때 사용)는 해당되지 않음

### max-width, min-width, max-height, min-height
  - 최대, 최소 너비
  - 최대, 최소 높이

### margin
  - 요소의 외부여백을 지정 
  - 부모요소의 가로너비의 퍼센트가 자식요소의 마진에 포함이 된다
  - 개별속성으로 top, right, bottom, left 가 있음
  - 마진중복이 발생할 수 있음
    - 형제 요소(margin-top)과 (margin-bottom)이 만났을 때
    - 부모 요소(margin-top)과 (margin-top)이 만났을 때
    - 부모 요소의(margin-bottom)과 자식 요소의(margin-bottom)이 만났을 때

### padding
  - 요소의 내부 여백을 지정
  -  패딩값을 같이 포함해서 너비를 계산하거나 box-sizing:border-box를 넣으면 됨

### border
  - 요소의 테두리 선을 지정
  - border-width : 선의 두께를 지정
  - border-style : 선의 종류를 지정 (top, left, right, bottom)
  - border-color : 선의 색깔
  - box-sizing : border-box 이거를 하게 되면 자동으로 선까지 포함해서 계산을 하게 해줌

### box-sizing
  - 요소의 크기 계산 기준을 지정
  - content-box : 너비(width,height)만으로 요소의 크기를 계산
  - border-box : 너비(width,height)에 안쪽 여백(padding)과 테두리 선(border)을 포함하여 요소의 크기를 계산

### display
  - 요소의 박스 타입을 설정
  - block, inline, inline-block, 기타(table, table-cell,flex), none

### overflow
  - 요소의 크기 이상으로 내용이 넘쳤을 때, 내용의 보여짐을 제어
  - visible, hidden, scroll, auto(스크롤바가 있고 자연스럽게 보일수 있도록 많이 사용함)

### opacity
  - 요소의 투명도를 지정
