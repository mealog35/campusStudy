# Part 20. 속성-Grid

### Grid
  - 2차원(행과 열)의 레이아웃 시스템을 제공
  - 파이어폭스 브라우저를 사용해 테스트할 것을 추천함
  - container 와 item이라는 두 가지 개념으로 구분되어 있음

### display
  - grid : block 처럼 쌓이겠다
  - inline-grid : inline처럼 수평으로 나열하겠다

### grid-template-rows, grid-template-columns
  - grid-template-rows : 명시적 행의 크기를 정의, 라인의 이름도 정의할 수 있음 
  - grid-template-columns : 명시적 열의 크기를 정의, 라인의 이름도 정의할 수 있음
```react
  .container{
  display:grid;
  grid-template-rows:repeat(2,100px); // 2번 반복하면서 100px로 맞추겠다
  grid-template-columns:repeat(3,1fr); // 3번 반복하면서 1비율로 맞추겠다
  border: 4px solid lightgray;
}
.item{
  border:2px dashed red;
}
  
```

### grid-row, grid-column
  - 음수로도 사용할 수 있음
  ![image](https://user-images.githubusercontent.com/80936709/127083968-92a1fb33-1901-4a7f-bc02-f3e9150c6626.png)
  
### grid-templaye-areas
  - 그리드 영역 이름을 참조해 그리드 템플릿을 생성
  - ![image](https://user-images.githubusercontent.com/80936709/127087295-0517bfde-b160-4820-ac2b-88490b64459f.png)

### row-gap, column-gap
  - row-gap : 각 행과 행 사이의 간격을 지정합니다
  - column-gap : 각 열과 열 사이의 간격을 지정합니다
  - gap : row-gap, column-gap

### grid-auto-rows, grid-auto-columns
  - 암시적 행의 크기를 정의 (음수를 사용할수 없음)
  - ![image](https://user-images.githubusercontent.com/80936709/127107424-fc860db4-b7ad-4abb-830e-234e9767cba5.png)


### grid-auto-flow
  - 배치하지 않은 아이템을 어떤 방식의 자동 배치 알고리즘으로 처리할지 정의함
  - row dense : 각 행 축을 따라 차례로 배치, 빈 영역 메움
  - column dense : 각 열 축을 따라 차례로 배치, 빈 영역 메움
  - ![image](https://user-images.githubusercontent.com/80936709/127107982-62b0a2db-dd59-4525-8466-69312769e507.png)

### grid-template-rows, grid-template-columns
  - 명시적 행의 크기를 정의함

### grid-row
  - grid-row-start / grid-row-end의 단축 속성
  - span이 start에 있으면 + end에 있으면 -가 됨
  - grid-area : grid-row-start / grid-column/start / grid-row-end / grid-column-end 이렇게 써야 함

### align-self
  - 단일 그리드 아이템을 수직정렬함

### justify-self
  - 단일 그리드 아이템을 수평정렬함

### grid functions
  - repeat() : 함수는 행/열 그기 정의를 반복함
  - minmax() : 함수는 행,열의 최소/최대 크기를 정의 첫번째 인수는 최솟값 두번째 인수는 최댓값
  - fit-content() : 그리드 아이템이 포함하는 내용 크기 최대를 맞춤 / 행 열 두가를 다 넣어줘야 함 ex) fit-content(300px) fit-content(300px)

### 단위
  - fr : 사용 가능한 공간에 대한 비율
  - min-content : 그리드 아이템이 포함하는 내용의 최소 크기를 의미함 / 한글일 경우에는 word-break:keep-all;을 해줘야 함
  - max-content : 그리드 아이템이 포함하는 내용의 최대 크기를 의미함
  - auto-fill, auto-fit : 행과 열의 개수를 그리드 컨테이너 및 행/열 크기에 맞게 자동으로 조정합니다 공간 여백이 남음/ 공간 여백이 없음 (두개의 차이점)
   
