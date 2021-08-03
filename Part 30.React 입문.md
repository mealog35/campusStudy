# Part Part 30.React 입문

### JSX
  - 두개의 태그는 <div></div>로 감싸야 함 / fragment를 사용할 수 있음
  - ![image](https://user-images.githubusercontent.com/80936709/127967794-4cc12b90-42c4-429f-b1a4-667cead3624d.png)

### props 
  - ![image](https://user-images.githubusercontent.com/80936709/127970442-f9c1c856-d380-4be6-8d7b-f4cc8f8a0faa.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127971303-c94f6e09-50f1-49fa-b02b-6ef06314aedd.png)

### 조건부 렌더링
  - 특정 조건에 따라 렌더링을 함

### useSstate
  - 사용자 인터랙션에 따라 바뀌어야 할 때
  - ![image](https://user-images.githubusercontent.com/80936709/127973437-723c5d47-543c-4a41-bc9b-d0141bc8f613.png)

### input 상태 관리
  - ![image](https://user-images.githubusercontent.com/80936709/127974815-d20b45be-480f-462b-a469-11d7d98055eb.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127977680-2eea83f5-b2c9-4450-80a4-29ec6e23181e.png)
  - 객체상태 관리할 경우에는 스프레드 함수를 넣어서 하면 됨

### useRef로 특정 DOM 선택하기
  - ![image](https://user-images.githubusercontent.com/80936709/127978601-fbc654fb-1abf-4efe-90d6-278ea6ad95e5.png)

### 배열 렌더링 하기
  - ![image](https://user-images.githubusercontent.com/80936709/127979504-da0f88be-9e73-4a68-9ee4-a3aa690cdc69.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127980178-33ce734e-120c-4e6c-96b7-deab16487381.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127980473-c78541a5-f4cb-4dca-8629-c29c9e8cc7dc.png)

### useRef 변수 만들기
  - 값이 바뀌어도 컴포넌트가 리렌더링 되지 않음

### useEffect
  - 컴포넌트가 마운트 됐을 때 (처음 나타났을 때), 언마운트 됐을 때 (사라질 때), 그리고 업데이트 될 때 (특정 props가 바뀔 때)

### useCallback
  - 함수를 재사용할 경우에 씀
  - React.memo를 이용해서 리렌더링을 방지함

### useReducer
  - 액션이라는 것을 기반으로 업데이트를 함
  - useState 대신에 사용함
  - ![image](https://user-images.githubusercontent.com/80936709/128003315-a4e3b842-2804-4586-bb69-adefa493145c.png)










