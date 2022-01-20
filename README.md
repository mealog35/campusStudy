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

function A(){}

let obj = new A(); 
