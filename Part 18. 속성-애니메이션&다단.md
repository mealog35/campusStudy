# Part 18. 속성-애니메이션&다단

### animation 
  - 요소에 애니메이션을 설정/제어
```react
  .box:hover{
    animation:first-animation 2s infinite alternate; //저 애니메이션을 2초동안 무한반복하고 다시 원래상태로 자연스럽게 돌아오게하겠다
    }
    @keyframes first-animation{
      0%{
        width:100px;
      }
      100%{
        width:500px; // 길이 크기에 따라서 지정할 수가 있음 중간50%도 할수가 있음
      }
    }
```
  - animation-name : 이름을 지정
  - animation-duration : 지속시간 (.3s) 이렇게 사용할 수 있음
  - animation-timing-function : 타이밍 함수지정
    - ease : 빠르게 - 느리게
    - linear : 일정하게
    - ease-in : 느리게 - 빠르기
    - ease-out : 빠르게 - 느리게
    - ease-in-out : 느리게 - 빠르게 - 느리게
    - cubic-bezier(n,n,n,n) : 자신만의 값을 정의
    - steps(n) : n번 분할된 애니메이션
  - animation-delay : 애니메이션의 대기 시간 설정 (음수로 설정할수 있음)
  - animation-iteration-count : 애니메이션의 반복 횟수를 설정 / infinite 무한으로 설정할 수 있음
  - animation-direction : 애니메이션의 반복 방향을 설정
    - normal : 정방향만 반복
    - reverse : 역방향만 반복
    - alternate : 정방향에서 역방향으로 반복(왕복)
    - alternate-reverse : 역방향에서 정방향으로 반복(왕복)
    - animation-fill-mode : 애니메이션의 전후 상태를 설정
      - none : 기존위치에서 시작 -> 애니메이션 시작 위치로 이동 -> 동작 -> 기존위치에서 긑
      - forwards : 기존위치에서 시작 -> 애니메이션 시작 위치로 이동 -> 동작 -> 애니메이션 끝 위치에서 끝
      - backwards : 애니메이션 시작 위치에서 시작 -> 동작 -> 기존 위치에서 끝
      - both : 애니메이션 시작 위치에서 시작 -> 동작 -> 애니메이션 끝 위치에서 끝
    - animation-play-state : 애니메이션의 재생과 정지를 설정 (pased)

### Multi-Columns
  - 일반 블록 레이아웃을 확장하여 여러 텍스트 다단으로 쉽게 정리하며, 가독성 확보
  - columns : column-count(단의 개수) column-width(각 단의 너비) column-rule(선의 스타일,사이즈) column-gap(단의 선 양쪽의 갭)
```react
  p{
    columns: 150px 3; //최소너미 단의개수
```
  - column-gap : 단과 단 사이의 간격 설정
  - column-rule : 단과 단 사이의 선을 지정
    - column-width : 선의 두게를 지정
    - column-style : 선의 종류를 지정
    - column-color : 선의 색상을 지정 (color의 영향을 받기 때문에  색을 따로 지정해 줘야 함)
