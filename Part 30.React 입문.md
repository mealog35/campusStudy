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

### UseReducer

```React.dom

import React, { useReducer, useState } from 'react';

//reducer dispatch action

const ACTION_TYPES = {
    deposit:'deposit',
    withdraw : 'withdraw'
}

const reducer = (state,action) =>{
    console.log("reducer",state, action)
    switch(action.type){
        case ACTION_TYPES.disposit:
            return state + action.payload
        case ACTION_TYPES.disposit:
            return state - action.payload
        default:
            return state
    }
}

function Bank ()  {
    const [number,setNumber] = useState(0);
    const [money, dispatch] = useReducer(reducer,0)
    return (
        <div>
            <h2>useReducer</h2>
            <p>잔고 : {money}</p>
            <input
                type="number"
                value={number}
                onChange={(e)=>{setNumber(parseInt(e.target.value))}}
                step="1000"
            />
            <button onClick={()=>dispatch({type:ACTION_TYPES.disposit, payload: number})}>예금</button>
            <button onClick={()=>dispatch({type:ACTION_TYPES.withdraw, payload: number})}>출금</button>
        </div>
    );
};

export default Bank;

```

```React.dom

import React, { useReducer, useState } from 'react';
import Name from './Name';

const Student = () => {
    const reducer = (state, action) =>{
        switch(action.type){
            case "add-studnet":
                const name = action.payload.name
                const newStudent = {
                    id : Date.now(),
                    name,
                    isHere:false
                };
                return {
                    count: state.count + 1,
                    students:[...state.students, newStudent]
                };
            case 'delete-student':
                return{
                    count : state.count -1,
                    students: state.students.filter(student => student.id !== action.paload.id)
                }
            case 'mark-student':
                return{
                    ...state,
                    students: state.students.map(student=>{
                        if(student.id === action.paload.id){
                            return{...student, isHere:!student.isHere}
                        }
                        return student
                    })
                }
            default:
                    return state;
        }
    }
    const initialState ={
        count: 0,
        students:[]
    }
    const [name, setName] = useState('');
    const [studentsInfo, dispatch] = useReducer(reducer, initialState)
    return (
        <div>
            <h1>출석부</h1>
            <p>총 학생 수 : {studentsInfo.count} </p>
            <input
                type="text"
                placeholder='plase your name...'
                value={name}
                onChange={(e)=>setName(e.target.value)}
            />
            <button onClick={()=>{
                dispatch({type:'add-studnet', payload:{name}})
            }}>add</button>
            {studentsInfo.students.map((student)=>{
                return(
                    <Name 
                        key={student.id} 
                        name={student.name} 
                        dispatch={dispatch} 
                        id={student.id} 
                        isHere={student.isHere}
                    />
                ) 
            })}
        </div>
    );
};

export default Student;

import React from 'react';

const Name = ({name, dispatch, id,isHere}) => {
    return (
        <div>
            <span 
                style={{
                    textDecoration:isHere ? 'line-through' : 'none',
                    color: isHere ? "gray" : "black"
                }}
                onClick={()=>{
                    dispatch({type:'mark-student', paload:{id}})
                }}
            >{name}</span>
            <button onClick={()=>{dispatch({type:'delete-student', paload:{id}})}}>삭제</button>
        </div>
    );
};

export default Name;

```

### Context
- props를 일일이 다 바꿔주지 않아도 됨
- 컴포넌트를 재사용하기 어려워 질수 있음
- 전역적인 데이터로 쓰기 위함

```React.dom
//context folder > ThemeContext.js
import { createContext } from "react";
export const ThemeContext = createContext(null);

//Hong,js
const Hong = () => {
    const [isDark, setIsDark] = useState(false);

    return (
        <ThemeContext.Provider value={{isDark, setIsDark}}>
            <Page/>
        </ThemeContext.Provider>
    );
};

export default Hong;

//page.js
const Page = () => {
    const data = useContext(ThemeContext);
    console.log(data);
    return (
        <div className='page'>
            <Header/>
            <Content/>
            <Footer/>
        </div>
    );
};

//header.js
const Header = () => {
    const {isDark} = useContext(ThemeContext);
    return (
        <header
            className='header'
            style={{
                backgroundColor:isDark? 'black':'lightgray',
                color:isDark? 'white':'black'
            }}
        >
            <h1>홍길동 웰컴!</h1>
        </header>
    );
};

//content.js
const Content = () => {
    const {isDark} = useContext(ThemeContext);

    return (
        <div
            className='content'
            style={{
                backgroundColor:isDark? 'black':'lightgray',
                color:isDark? 'white':'black'
            }}
        >
            <h1>홍길동 좋은하루 되세요</h1>
        </div>
    );
};

//footer.js
const Footer = () => {
    const {isDark,setIsDark} = useContext(ThemeContext);

    const toggleTheme = ()=>{
        setIsDark(!isDark)
    };

    return (
        <footer
            className='footer'
            style={{
                backgroundColor:isDark? 'black':'lightgray',
            }}
        >
            <button className='button' onClick={toggleTheme}>Dark Mode</button>
        </footer>
    );
};
```
 
 ### useRef
 - ref는 랜더링을 시키지 않음
 - 값을 유지시킴
 
 ```React.dom
 //ref 전달하는 방법
    const inputRef = useRef();
    const focus = () =>{
        inputRef.current.focus();
    }

    return (
        <>
            <Page ref={inputRef}/> //1
            <Page inputRef={inputRef}/> //2
            <button onClick={focus}>focus</button>
        </>
    );
};
 
//Page.js
const Page = (props,ref) => {
    // const data = useContext(ThemeContext);
    // const name = useContext(UserContext);
    // console.log(data);
    return (
        <input ref={ref}/>
    );
};

export default forwardRef(Page);

const Page = ({inputRef}) => {
    console.log(inputRef);
    return (
        <input ref={inputRef}/>
    );
};

export default (Page);
 ```
###index.js
- 리액트 v18에선 ReactDom.render이 더이상 지원되지 않기때문에 createRoot를 사용해야 함
- const root = ReactDOM.createRoot(document.getElementById('root')); 변수로 담아서 사용

```React.dom

import React from 'react';
import * as ReactDOM from 'react-dom/client';
import { Provider } from 'react-redux';
import { legacy_createStore } from 'redux';
import App from './App';
import './index.css';
import rootReducer from './modules';
import reportWebVitals from './reportWebVitals';

const store = legacy_createStore(rootReducer);
//미들웨어를 여러개 적용시킬 수 있음
//const store = legacy_createStore(rootReducer,applyMiddleware(myLogger,logger));
const root = ReactDOM.createRoot(document.getElementById('root'));

root.render(
  <Provider store={store}>
    <App/>
  </Provider>
  // document.getElementById('root')
);

```

###리덕스 로거 미들웨서 사용법

```React.dom

import React from 'react';
import * as ReactDOM from 'react-dom/client';
import { Provider } from 'react-redux';
import { applyMiddleware, legacy_createStore } from 'redux';
import { composeWithDevTools } from 'redux-devtools-extension';
import logger from 'redux-logger';
import App from './App';
import './index.css';
import myLogger from './middlewares/myLogger';
import rootReducer from './modules';
import reportWebVitals from './reportWebVitals';

//미들웨어를 여러개 적용시킬 수 있음
const store = legacy_createStore(rootReducer,composeWithDevTools(applyMiddleware(logger)));
const root = ReactDOM.createRoot(document.getElementById('root'));

root.render(
  <Provider store={store}>
    <App/>
  </Provider>
  // document.getElementById('root')
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();

```
  - ![image](https://user-images.githubusercontent.com/80936709/192463315-5a902742-0de3-4aec-b4b5-f7a52101bf47.png)

###connect

```React.dom

  import { connect, useDispatch, useSelector } from "react-redux";
  import Counter from "../components/Counter";
  import { decrease, increase,setDiff } from "../modules/counter";

    function CounterContainer({number,diff,onSetDiff,onIncrease,ondecrease}){
        return(
            <Counter
                number={number}
                diff={diff}
                onSetDiff={onSetDiff}
                onIncrease={onIncrease}
                ondecrease={ondecrease}
            />
        )
    }
    
    // const {number, diff} = useSelector(state => ({
    //     number : state.counter.number,
    //     diff : state.counter.diff
    // }));
    // const number = useSelector(state => state.counter. number);
    // const diff = useSelector(state => state.counter. diff);
    const mapStateToProps = state =>({
        number : state.counter.number,
        diff : state.counter.diff
    });
    
    // const dispatch = useDispatch();
    // const onSetDiff = () => dispatch(setDiff(diff))
    // const onIncrease = () => dispatch(increase())
    // const ondecrease = () => dispatch(decrease())

    const mapDispatchToProps = dispatch =>({
        onIncrease : () => dispatch(increase()),
        ondecrease : () => dispatch(decrease()),
    })

    //connect
    export default connect(
        mapStateToProps,
        mapDispatchToProps
    )(CounterContainer);

    // const enhance = connect(mapStateToProps,mapDispatchToProps);
    // export default enhance(CounterContainer)

```







