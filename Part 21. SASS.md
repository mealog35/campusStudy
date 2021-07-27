# Part 21. SASS

### 주석
  - //컴파일이 되지 않는 주석
  - /* 컴파일이 되는 주석 */
  - 주석 처리 할 때에도 줄 간격을 맞춰야 함

### 데이터 종류
  - numbers : 숫자
  - strings : 문자
  - colors : 색상 표현
  - booleans : 논리
  - null : 아무것도 없음
  - lists : 공백이나 , 로 구분된 값의 목록
  - maps : list와 유사하나 값이 key:value 형태 / 객체와 매우 비슷함

### 중첩
```react
.container{
    $size:100px;
    .item{
        width:$size*3;
        height:$size;
        background:tomato;
    }
}
```
  - 상위 선택자 참조
```react
.btn{
  position:absolute;
  &.active{
    color:red;
    }
  }
  .list{
    li{
      &:last-child{
      margin-right:0;
      }
    }
  }
  <!--css 버전-->
  .btn{
    position:absolute;
  }
  .btn.active{
    color:red;
  }
  .list li:last-child{
    margin-right:0;
  }
```

### 중첩 벗어나기
  - @at-root 사용해서 중첩에서 벗어나게 하기
  ![image](https://user-images.githubusercontent.com/80936709/127128964-e4793fa3-0edb-447d-bdcb-1f8bc762e65c.png)
  
### 변수
  - 반복적으로 사용되는 값을 변수로 지정할 수 있음
  - $변수이름 : 속성값;
  - 변수 유효범위를 가지고 있어서 그 안에서만 사용할 수 있음
  - !global(전역설정)으로 할 수 있음 / $color: #111 !global;
  - !default 초깃값 설정해서 기존 값을 가지고 오게 함
  - #{} 문자를 보관할 수 있음 / inwuote()는 문자에서 따옴표를 제거함

### 가져오기
  - @import
    - 파일 확장자가 .css일 때
    - 파일 이름이 http://로 시작하는 경우
    - url() 이 붙었을 경우
    - 미디어쿼리가 있는 경우

### 연산
  - 오른쪽 값이 숫자여야만 함 ex) 10px * 10px (x) 10px * 10(o)
  - 상대적 단위 연산 calc() 연산을 이렇게 해야 함 ex)calc(50% - 20px) 
    - 나누기 연산 : 변수로 저장되거나 함수에 의해 반환되는 경우
      - 값이 ()로 묶여 있는 경우
      - 값이 다른 산술 표현식의 일부로 사용되는 경우
    - 문자 : 첫 번째 피연산자에 따옴표가 붙어 있다면 따옴표가 같이 나오고, 첫 번째 피연산자에 따옴표가 없다면 따옴표가 없게 나옴
    - 색상 : opacity 더 불투명하게 transparentize 더 투명하게 함
    - 논리 : 그리고, 또는, 부정 이 있습니다

### 재활용
  - mixins 정의 하는 것 include가 사용하는 것
  ![image](https://user-images.githubusercontent.com/80936709/127139640-39cb0126-5010-4a67-b708-7d459d730112.png)
  - 인수 : 매개변수라고 생각하면 됨
  - 가변 인수 : 인수의 개수가 불확실한 경우가 있음 그러면 매개변수 뒤에 ...을 붙여줌
  - @content : 해당 부분에 원하는 스타일 블록을 전달할 수 있음 (속성추가)
![image](https://user-images.githubusercontent.com/80936709/127147837-06529cd6-9fef-4d56-93bc-8d8332701521.png)
  - 확장 : @extend 다른 선택자의 모든 스타일을 가져야하는 경우에 사용함
