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

### useMemo
  - 필요한 경우에만 리랜더링 되도록 하기
  - 연산된 값을 재 사용할 경우

### useCallback
  - 특정함수를 재사용할 경우에 씀
  - React.memo를 이용해서 리렌더링을 방지함

### useReducer
  - 액션이라는 것을 기반으로 업데이트를 함
  - useState 대신에 사용함
  - ![image](https://user-images.githubusercontent.com/80936709/128003315-a4e3b842-2804-4586-bb69-adefa493145c.png)

### createContext
  - 컴포넌트 통해서 값을 전달 받는것이 아니라 바로 사용할 수 있도록 하는 것
  - provider가 내장되어 있음
  - dispatch 여러컴포넌트를 거치지 않고 사용할 수 있음

### immer
  - 불변성을 유지해줌

### FirwardRef
  - Ref 전달

```react.dom
///App.js
function App() {
  const inputRef = useRef();

  const focus = () =>{
      inputRef.current.focus();
  };
  return (
    <div className="App">
      <User ref={inputRef}/>
      <button onClick={focus}>button</button>
    </div>
  );
}


///User.js
import React, { forwardRef } from 'react';

const User = (props,ref) => {

    return (
        <input ref={ref}/>
    );
};

export default forwardRef(User);
```

### UseMemo
- useMemo를 통해 캐싱해놓은 값을 가지고 옴
- 함수의 연산량이 많을때 이전 결과값을 재사용 하는 것이 목적

```React.dom
import { useEffect, useMemo, useState } from 'react';

  const hardCalculate = (number) =>{
    console.log("hardCalculate");
    for(let i = 0; i<99999999; i++){}
    return number +10000;
  }

  const easyCalculate = (number) =>{
    console.log("easyCalculate");
    return number +1;
  }

function App() {
  const [hardNumber, setHardNumber] = useState(1);
  const [easyNumber, setEasyNumber] = useState(1);

  // const hardSum = hardCalculate(hardNumber)
  const hardSum = useMemo(()=>{
    return hardCalculate(hardNumber)
  },[hardNumber])
  
  const easydSum = easyCalculate(easyNumber)
  return (
    <div className="App">
      <h3>hardCalculate</h3>
      <input
        type="number"
        value={hardNumber}
        onChange={(e)=>setHardNumber(parseInt(e.target.value))}
      />
      <span>+ 1000= {hardSum}</span>

      <h3>easyCalculate</h3>
      <input
        type="number"
        value={easyNumber}
        onChange={(e)=>setEasyNumber(parseInt(e.target.value))}

      />
      <span>+ 1= {easydSum}</span>
    </div>
  );
}

export default App;
```

```React.dom
//useMemo 사용법
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);


import React, { useEffect, useMemo, useState } from 'react';

function App () {
  const [number, setNumber] = useState(0);
  const [isKorea, setIsKorea] = useState(true);

  // const location = isKorea ? '한국' : '외국';
  const location = useMemo(()=>{
    return{
      country : isKorea ? '한국' : '외국'
    };
  },[isKorea])
  // object로 할 경우에는 useEffect 에 있는 인자값이 같은 변수임을 인지하지 못함
  // const location = {
  //   country : isKorea ? '한국' : '외국'
  // }

  useEffect(()=>{
    console.log("useEffect")
  },[location]);

  return (
    <div>
      <h2>하루에 몇끼 먹어요?</h2>
      <input
        type="number"
        value={number}
        onChange={(e)=>setNumber(e.target.value)}
      />
      <hr/>
      <h2>어느 나라에 있어요?
      <p>나라 : {location.country}</p>
      <button onClick={()=> setIsKorea(!isKorea)}>뱅기타자</button>
      </h2>
    </div>
  );
};

export default App;
```

### UseCallback
- 함수가 재생성 되는것을 방지하기 위한 목적

```React.dom

import React, { useCallback, useEffect, useState } from 'react';

function Test () {
    const [ number , setNumber] = useState(0);
    const [toggle, setToggle] = useState(true);

    const someFunction = useCallback(() =>{
        console.log(`someFunc : number :${number}`);
        return ;
    },[number]); 
    
    useEffect(()=>{
        console.log("someFunction change")
    },[someFunction])

    return (
        <div>
            <input
                type="number"
                value={number}
                onChange={(e) =>setNumber(e.target.value)}
            />
            <br/>
            <button onClick={()=>setToggle(!toggle)}>{toggle.toString()}</button>
            <button onClick={someFunction}>dd</button>
        </div>
    );
};

export default Test;

```
 








