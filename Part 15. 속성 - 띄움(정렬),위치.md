# Part 15. 속성 - 띄움(정렬),위치

### float
  - 요소를 좌우 방향으로 띄움(수평 정렬) / 무조건 해체를 해줘야 함
  - flex를 사용하여 많이 쓰게 됨
  - 해제 방법 : 형제 요소에서 해제 , 부모 요소에서 해제 (clearfix 클래스를 추가함)
```react
  .clearfix::after{
    content:"";
    clear:both;
    display:block;
 }
 ```
 ### diplay 
  - 성질을 바꿔버림
  - float: right -> display: block 요소가 들어가 있음

### position (reative, absolute, fixed, sticky)
  - 요소의 위치 지정 방법의 유형을 설정
  - reative : 부모요소 (본인이 있는 그 기준에서 (top, left, right, bottom))를 해주면 본인이있는 기준으로 위치가 변경이 됨)
  - absolute : 부모요소(위치상) 설정해 줘야 함
  - fixed : 고정시킴(쇼핑몰 장바구니 같은거)
  - sticky : 스크롤 영역 기준으로 배치 (IE 지원불가) /해당 영역에서만 보이도록 하겠다
  - z-index : position이 있을 때만 작동하고 가장 앞으로 보이게 함(숫자가 높을수록)
  - position 사용하면 display:block 으로 자동 바뀌게 됨

