## 자바스크립트 객체

```C
 [객체 안에 함수]
  function Add(a,b){
    this.a = a;
    this.b = b;
    this.plus = function(){}
      return this.a + this.b;    
    }
    
  let add1 = new Add(100,20) // Add{a:100, b:20, plus:f}
  
  Add2.prototype.plus = function(){
    return this.a + this.b;
    }
```
- 생성자 함수와 new 연산자에 의해 새로운 객체 생성 --> 어떤 편리한 장점 --> 객체의 생성과 새로운 객체의원형(프로토타입)을 지정
- 뿐만 아니라, 괄호안에 (111,222)와 같은 초기화 값을 생성시에 편리하게 지정 --> 새로운 객체 인스턴스를 생성

## 프로토타입 객체의 속성

- constructor 속성 : 이 속성은 함수를 가리킨다 --> 참조 --> 즉, 참조를값으로 가지는 속성
- 서로가 참조 (이 말은 서로가 연결고리 역할을 함) : 생성자 함수 (prototype) 프로토타입 객체(constructor)

```C

function Animal(name,age){
 this.name = name;
 this.age = age;
}
Animal.prototype.aaa = function(){ console.log('aaa');}

function Animal2(name,age){
 this.name = name;
 this.age = age;
}
Animal2.prototype.bbb = function(){ console.log('bbb);}                                                                                                                   
let a1 = new Animal('tiger',20);
a1.aaa(); //aaa
a1.bbb(); //bbb

## 자바스크립트 프로토타입 상속

- 자바스크립트는 객체지향 언어인가?

==>그렇다 // 다만 다른 언어와는 달리 프로토타입 상속에 기반을 둔 OOP 언어

==>프로토타입 상속을이해하기 위해서는 객체 안에 함수 등 이런 부분을 기억해야 함

- 상속의 필요성

==> 가장 큰 목적 --> 재사용

==> 이미 부모쪽에서 정의된 속성과 메서드를 그대로 물러받아 재사용할 수 잇다 -->큰 장점

===>뿐만 아니라 새로운 기는을 추가해서 기존 가능성에 더 확장시킬 수 잇다 -->큰 장점

==>한맏로, 중복해서 또 작성하지 않아서 좋고, 필요에 따라서는 더 확장도 가능함

- 프로토타입 체인

==> (_proto_) --> 상속을해준 부모(원형)를 가리킴

==>자식 객체가 _proto_가 가리키는 부모 객체의 멤버 (속성, 메서드)를 사용할 수 있다 // 즉, 상속 받음


```C
 [객체]

let obj1 = {
name:'hong gil dong',
age:20,
sayHi:function(){console.log(""Hi~"+ this.name);};
}

let obj2 = {
name : 'lee sun shin"
}

obj2 객체의 _proto_ 속성은? object(최상위)
obj2._proto_ = obj1; (obj2의 부모 속성이 obj1으로 바뀜)
obj2.sayHi() // Hi~lee sun shin

```


- 빈 객체 생성 후 --> _proto_ 속성에 원하는 객체(부모가 될 또는 원형이 될)를 할당 -->상속

```C

let obj3={};

//지금 상태의 obj3의 객체의 원형(부모) = object ( 최상위, Object.prototype) --> null

//obj3의 부모(원형)을 바꾸면?
obj3_proto_ = obj2;

//hasOwnProperty(메소드는 객체가 특정 프로퍼티를 가지고 있는지를 나타내는 불리언(boolean) 값을 반환)
console.log(obj3.hasOwnProperty('asss')) // false

```

function A(){} // obj._proto_ => A()

let obj = new A();  //Object.getPrototypeOf(obj) => A()

function B() {}
let obj2= new B()

obj2._proto_===Object.getPrototypeOf(obj2) // true

- 내부적으로는 빈 객체를 생성한 후에 --> 같은 이름의 "프로토타입 객체"를 새로운 객체의 원형(프로토타입)으로 설정

```C

function Add(a,b){
 this.a = a;
 this.b = b;
 
}

Add.prototype.plus = function(){
return this.a + this.b
}
```

#### for ..in
- 위 코드에서 마지막에 생성한 객체 -> for ..in 반복문으로 순회 --> 결과는 프로토 타입 체인으로 연결되어 있는 원형(부모)의 멤버(속성,메서들)들이 다 나온다

- object.keys() vs Object.value() // 앞에 key 값이 나옴 vs 뒤에 내용이 나옴

next() 메서드와 yield

### setTimeout vs setInterval

- 비동기 처리에는 다양한 방법들이 존재 --> Promise와 Generator 함수를 이용한 비동기 처리

-호출 스케쥴링 함수 --> setTimeout(),setInterval()
- setTimeout                           setInterval
- 일정시간 "후에" 함수를 1번만 실행       일정시간 "마다" 함수를 주기적으로 실행
- clearTimeout                          clearInterval

### Promise와 Generator 함수를 이용한 비동기 처리

### Promise로 변환
1. new Promise() 호출하면 --> 대기(Pending)상태
2. 이때, 콜백 함수를선언할 수 있고 -> 인자는 resolve, reject
3. 콜백 함수내에서 처리할거 처리한 후 --> resolve() 호출 --> 이행(Fulfilled)상태
4. 성공이면 --> 리턴 값을 --> then()이 받아서 계속 처리 수행

```C
new Promise((resolve,reject) => {
 //처리
 setTimeout(
  (x) =>{
   let result = x;
   console.log(result);
   resolve(result);
 ),
 1000,
 10
})
 .then((result) =>{
   return new Promise((resolve,reject)) =>{
     setTimeout(
      (x) =>{
       result *= x;
       console.log(result);
       resolve(result);
     ),
     1000,
     20
   });
  })
```

- Promise와 Generator 함수를 이용한 비동기 처리 - Generator로 변환

```C

 function* testGen(){
 
  const a = yield 10;
  console.log(a)
 }
 
 const iter = testGen()
 iter.next() // 값이 없는 걸로 나옴 , 다만 콘솔로 찍었을 경우에 값이 나옴 {value : 10 , done: false}
 iter.next() // undefined {value : undefined , done : true}
 iter.next(1) // 1
 
 ```
 
