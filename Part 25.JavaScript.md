# Part 25.JavaScript

### Expression Statement
  - 표현식은 값을 만들어내기 때문에 함수의 인자로 사용할 수 있음
  - ![image](https://user-images.githubusercontent.com/80936709/127316296-48905a0a-0127-4f98-9fa3-96197175870f.png)

### Statement
  - 한 줄에 문장이 하나인 경우에는 세미 콜론을 붙이지 않아도 문제가 없습니다
  - 하지만, 관례적으로 붙입니다
  - 마지막 문장의 결과가 반환됩니다
  - 조건문(if), 반복문(for)도 문장입니다
  - 이 경우에는 마지막 } 뒤에 세미콜론을 붙이지 않습니다

### 키워드와 예약어
  - keywords : 자바스크립트에서 특정한 목적을 위해 사용하는 단어
  - 이러한 키워드 들은 예약어로 지정되어 있음
  - ex) var
  - Reserved Words : 프로그램을 작성할 때, 변수명, 함수명 등 이름을 사용할 수 없는 단어 ex)return , for
  - future reserved keywords : 앞으로 특정한 목적을 위해 사용할 가능성이 있어서 사용할 수 없는 예약어

### 식별자 (identifier)
  - 코드 내의 변수, 함수, 혹은 속성을 식별하는 문자열 / 대소문자 가 다르면 서로 다른 변수로 이해함
  - var 1name (x)
  - 적절한 이름을 지을 수 있도록 노력해야 함

### comments
  - 주석 : 소스코드에서 프로그램에 영향을 주지 않고, 무시되는 부분
  - 한 줄만 주석 // 를 사용하면 됨
  - 여러줄 주석 : /**/ 사용함
  
### 변수와 상수
  - const 상수를 지칭하는 이름 = 값 // 값이 변하지 않음
  - let 변수를 지칭하는 이름 = 값 // 값이 변할수 있음 var 함수 스코프
  - 유효범위
```react
  {
    const name = 'Mark'
    안에서만 사용할 수 있음
  }
    let age = 27 // 밖에서 선언할 경우에는 블럭 안에서도 사용할 수 있음
```
```react
  // 블록 스코프에서는 실행됨 하지만, 함수 스코프에서는 그 안에서만 실행 됨 그래서 const, let을 사용하는 거를 추천 함
  {
    var d =0;
    console.log(d);
  }
  console.log(d); //0 실행됨
```

### var 호이스팅
  - 아래있는 함수를 끌어 올린다
  - 호이스팅에 문제가 생겨서 사용하는거를 추천하지 않음
```react
  function hello1(){
    console.log('hello1');
  }

  hello1();

  hello2();
  function hello2(){
      console.log('hello2');
}
```react
  console.log(name); // undefinded

  name = 'Mark';

  console.log(name); // Mark

  var name = 'hello'; //var 가 호이스팅이 됨
```
```react
  console.log(name); // error 뜸

  name = 'Mark';

  console.log(name); // Mark

  let name; //let은 호이스팅이 되지 않음
```

### 자료형
  - 기본타입
    - boolean
      ```react
        //Boolean

        const a = new Boolean(false); // 객체
        console.log(a, typeof a); // [Boolean : false] , object 객체 자체는 true임

        const b = Boolean(false);
        console.log(b, typeof b); // false boolean
      ```
    - null
    - undefined
      ```react
        const a = null;
        console.log(a, typeof a); // null object 값이 없는 객체

        const b = undefined;
        console.log(b, typeof b); // undefined undefined
        // null과 undefined 정확한 구분을 위해서는 === 으로 비교를 해야 함
      ```
    - number
      ```react
        const a = 37;
        console.log(a, typeof a); // 37, number

        const b = NaN;
        console.log(b, typeof b); // Nan, number

        // NaN이 쓰이는 경우는 형변환을 할 경우에
        // 문자열이 숫자로 바껴야 하는데 바뀔 수 없는 경우
        const c = Number("Mark");
        console.log(c, typeof c);

        const d = Number("67");
        console.log(d, typeof d);
      ```
    - string
      ```react
        const e = "Mark";
        console.log(e, typeof e);//Mark string

        const f = "Mark" + "Lee";

        const g = e + "Lee";
        //template string `(백틱)을 사용함
        const h = `${e} Lee`;
        console.log(h, typeof h);//Mark Lee string
      ```
    - symbol(eECMAScript 6 추가 됨)
      ```react
        const a = Symbol();
        const b = Symbol(37);
        const c = Symbol("Mark");
        const d = Symbol("Mark");

        console.log(a, typeof a);//Symbol() symbol
        console.log(c === d);

        //new Symbol(); 사용할 수 없음
      ```
  - 객체 

### 조건문
  - 표현식이 참으로 평가될 때, 실행되는 블럭
  ```react
      if(true){
      console.log('항상 실행');
      }
      //블럭 코드가 한줄이면, 중괄호 {}는 생략 가능합니다
      if(false) console.log('항상 실행되지 않음');
  ```
  - 표현식이 거짓으로 평가될 때
  - 표현식이 참으로 평가될 때
  ```react
    //false
    //0
    //''
    //null
    //undefined
    //NaN

    if (false) console.log(false);
    if (0) console.log(false);
    if ("") console.log("");
    if (null) console.log(null);
    if (undefined) console.log(undefined);
    if (NaN) console.log(NaN);

    //true
    //37
    //-37
    //'Mark'
    //{}
    //[]

    if (true) console.log(true);
    if (37) console.log(37);
    if (-37) console.log(-37);
    if ("Mark") console.log("Mark");
    if ({}) console.log({});
    if ([]) console.log([]);
  ```
  - else
  ```react
    const n = 37;
    //블럭 안 문장이 하나일 경우 ,중괄호 없이 사용 가능
    if(n>0){
        console.log('n이 0 보다 큰 경우');
    } else{
        console.log('n이 0 보다 크지 않은 경우');
    }
  ```
  - else if{}
    - if에 해당되지 않을 때
    ```react
      // 이렇게 하면 헷갈릴수가 있음
      const n = 15;
      if (n % 3 === 0) {
        console.log("n은 3의 배수 입니다.");
      } else if (n % 5 === 0) {
        console.log("n은 5의 배수 입니다");
      } else {
        console.log("n은 3의 배수도 아니고, 5의 배수도 아닙니다");
      }
      //반복돼서 사용될 경우에는 변수를 이용하여 사용하면 편리함
      const multipleOfThree = (n % 3 ===0);
      const multipleOfFive = (n % 5 ===0);

      if (multipleOfThree && multipleOfFive) {
        console.log("n은 15의 배수입니다");
      } else if (multipleOfThree) {
        console.log("n은 3의 배수 입니다.");
      } else if (multipleOfFive) {
        console.log("n은 5의 배수 입니다.");
      } else {
        console.log("n은 3의 배수도 아니고, 5의 배수도 아닙니다");
      }
      //중첩으로 사용 가능함
      if (multipleOfThree && multipleOfFive) {
          console.log("n은 15의 배수입니다");
        }else{
           if (multipleOfThree) {
              console.log("n은 3의 배수 입니다.");
          } else if (multipleOfFive) {
              console.log("n은 5의 배수 입니다.");
          } else {
              console.log("n은 3의 배수도 아니고, 5의 배수도 아닙니다");
          }
      }   
    ```
    - 논리 연산자를 이용한 조건문 평가 (&& || !)
    ```react
      // &&
      if(true && true){
          console.log('두개 모두참이면 참')
      }
      if(true && false){
          console.log('한개만 참이면 거짓')
      }
      if(false && true){
          console.log('한개만 참이면 거짓')
      }
      if(false && false){
          console.log('한개만 참이면 거짓')
      }
      // ||
      if(true && true){
          console.log('두개 모두 참이면 참')
      }
      if(true && false){
          console.log('한개만 참이면 참')
      }
      if(false && false){
          console.log('두개 모두 거짓이면 거짓')
      }
      // !
      if(!true){
          console.log('참이면 거짓')
      }
      if(!false){
          console.log('거짓이면 참')
      }
    ```
    ```react
      let n = 7;
      n % 5 === 0 && console.log("5로 나누어 떨어질 때만 실행1");
      // 앞 표현식의 평가 결과가 거짓일때는 뒤 표현식을 평가할 필요가 없어서 실행하지 않는다
      n = 5;
      n % 5 === 0 && console.log("5로 나누어 떨어질 때만 실행2");
      // 앞 조건이 맞으면 실행 됨

      //앞 표현식을 평가를 해서 참이면, 뒤 표현식을 평가할 필요가 없어서 실행하지 않는다.
      n = 5;
      n % 5 === 0 || console.log("5로 나누어 떨어질 때만 실행되지 않음3");

      n = 6;
      n % 5 === 0 || console.log("5로 나누어 떨어질 때만 실행되지 않음4");
      // 앞 표현식을 평가해서 거짓 일때만, 뒤 표현식을 평가하게 됨
    ```
    - 삼항 연산자를 이용한 조건부 실행
      ```react
        const message = n % 5 === 0 ? "5의 배수 입니다" : "5의 배수가 아닙니다";
        console.log(message);
      ```
    - switch를 이용함
    ```react
      let n = 5;
      switch (n) {
        default:
          console.log(n);
      }
      // 5의 배수입니다 5 둘다 출력됨
      switch (n % 5) {
        case 0: {
          console.log("5의 배수입니다.");
        }
        default:
          console.log(n);
      }
      //break 문을 걸어서 5의 배수입니다만 나오도록 출력하기 case 값은 조건문안의 결과값 내용
      switch (n % 5) {
        case 0: {
          console.log("5의 배수입니다.");
          break;
        }
        default:
          console.log(n);
      }
      n = 8;
      switch (n % 5) {
        case 0: {
          console.log("5의 배수입니다.");
          break;
        }
        case 1:
        case 2:
        case 3:
        case 4:
        case 5:
          console.log(n);
        default:
          console.log(n);
      }
    ```
    - 반복문 for(초기화; 반복 조건; 반복이 된 후 실행되는 코드){반복이 되는 코드 블럭} / 
    - for(;;){d} // 무한루프
    ```react
      while(조건){
        조건이 거짓이 될 때까지 반복 실행
      }
      do{
        조건이 거짓이 될 때까지 반복 실행
      }while(조건);
    ```
    - for of // iterable
    - for in // 모든 프로퍼티를 담을 수 있음
    ```react
      function hello1() {
      console.log("hello1");
      }
    ```
    - function vs new Function
    ```react
      global.a = 0;
      {
        const a = 1;

        const test = new Function("return a");

        console.log(test());
      }
      {
        const a = 2;

        const test = function () {
          return a;
        };
        console.log(test());
      }

    ```
    ```react
      console.log(hello1, typeof hello1);
      //매게변수를 이용하여 넣을 수 있음
      function hello2(name) {
        console.log("hello2", name);
      }
      function hello3(name) {
        return `hello3 ${name}`;
      }

      console.log(hello3("Mark"));
    ```
    - () =>{}
    ```react
      const hello = () => {
      console.log("hello1");
      };

      const hello2 = (name) =>{
          console.log('hello2',name);
      };

      const hello3 = (name, age) =>{
          console.log('hello3', name, age);
      };

      const hello4 = name =>{
          return `hello4 ${name}`;
      }

      const hello5 = name => `hello5 ${name}`
    ```
    - new 함수();
    ```react
      function Person(name, age) {
      console.log(this);
      this.name = name;
      this.age = age;
      }

      const p = new Person("Mark", 37);
      console.log(p, p.name, p.age);

      const a = new Person("Anna", 26);
      console.log(a, a.name, a.age);

      // 화살표 함수에서는 this를 사용할 수가 없음
      const Cat = (name, age) => {
        this.name = name;
        this.age = age;
      };

      const c = new Cat("냥이", 33);
      console.log(c, c.name, c.age);
    ```
    - 함수 안에 중첩 가능
    ```react
      //함수를 호출하면 함수를 만들어서 리턴
      function plus(base) {
        return function (num) {
          return base + num;
        };
      }

      const plus5 = plus(5);
      console.log(plus5(10));

      const plus7 = plus(7);
      console.log(plus7(8));
    ```
    - 함수를 호출할 때, 인자로 함수를 사용 (콜백)
    ```react
      function hello(c) {
      console.log("hello");
      c();
      }
      hello(function () {
        console.log("callback");
      });
    ```
    
### 객체 (object)
  - 함수, 클래스 (틀) => 객체, 개체, object
  ```react
    //값을 속성으로 넣기
    function A() {
      this.name = "Mark";
    }
    const a = new A(); //{ name: 'Mark' }
    console.log(a);

    //함수를 속성으로 넣기
    function B() {
      this.hello = function () {
        console.log("hello");
      };
    }
    new B().hello();
  ```
  - new Object()
  ```react
    // new Object
      const a = new Object();

      console.log(a, typeof a);//{} object

      const b = new Object(true);

      console.log(b, typeof b);//[Boolean: true] object

      const c = new Object({ name: "Mark" });

      console.log(c, typeof c);//{ name: 'Mark' } object
  ```
  -프로토타입 체인 (모든 객체들을 연결할 수 있음)
  ```react
        // prototype

          function Person(name, age) {
            this.name = name;
            this.age = age;
            //   this.hello = function () {
            //     console.log("hello", this.name, this.age);
            //   };
          }
          Person.prototype.hello = function () {
            console.log("hello", this.name, this.age);
          };

          const p = new Person("Mark", 37);
          p.hello();// hello Mark 37
          console.log(p.toString());// [object Object]
          console.log(Person.prototype);
          console.log(Person.prototype.toString);//[Function: toString]
          console.log(Person.prototype.constructor);//[Function: Person]
          console.log(Person.prototype.hello);

          console.log(Object.prototype);//{}
          console.log(Object.prototype.toString);//[Function: toString]
          console.log(Object.prototype.constructor);//[Function: Object]

          console.log(p instanceof Person);//true
          console.log(p instanceof Object);//object로 부터 person이 받아와서 둘다 true가 나옴
  ```
  - 프로토타입을 이용한 객체 확장
  ```react
        //prototype 상속
          function Person() {}

          Person.prototype.hello = function () {
            console.log("hello");
          };

          function Korean(region) {
            this.region = region;
            this.where = function () {
              console.log("where", this.region);
            };
          }
          Korean.prototype = Person.prototype;

          const k = new Korean("Seoul");
          k.hello();
          k.where();

          console.log(k instanceof Korean);
          console.log(k instanceof Person);
          console.log(k instanceof Object);
  ```
  ```react
        //객체 리터럴

        const a = {};

        console.log(a, typeof a);

        const b = {
          name: "Mark",
        };

        console.log(b, typeof b);

        const c = {
          name: "Mark",
          hello1() {
            console.log("hello1", this.name);
          },
          hello2: function () {
            console.log("hello2", this.name);
          },
          hello3: () => {
            console.log("hello3", this);//arrow 함수이기 때문에 this가 먹지 않음
          },
        };
        c.hello1();
        c.hello2();
        c.hello3();

  ```
  - 표준 내장 객체
  ```react
        // 표준 내장 객체 : Array

        const a = new Array("red", "black", "white");

        console.log(a, typeof a); //[ 'red', 'black', 'white' ] object

        const b = ["red", "green", "yellow"];

        console.log(b, typeof b);
        console.log(b instanceof Array);
        console.log(b instanceof Object);

        console.log(b.slice(0, 1));
        console.log(Array.prototype.slice, Object.prototype.slice);//[Function: slice] undefined
        //Array에 내장되어 있는 함수라서 Object에는 undefinded가 뜸
  ```
      
 ### 클래스
  -객체를 만들 수 있는 새로운 방법
```react
  //선언적 방식
    class A {}

    console.log(new A()); //A {}
    //class 표현식을 변수에 할당
    const B = class {};

    console.log(new B()); //B {}

    //선언적 방식이지만 호이스팅은 일어나지 않는다
```
  - constructor (생성자)
```react
  // constructor 생성자

      class A {}

      console.log(new A());

      class B {
        constructor() {
          console.log("constructor");
        }
      }

      console.log(new B());

      class C {
        constructor(name, age) {
          console.log("constructor", name, age);
        }
      }
      console.log("lee", 377);
      console.log(new C());//undefined undefined
```
  - 멤버 변수
```react
  //멤버 함수
  class D {
    hello1() {
      console.log("hello1", this);
    }

    hello2 = () => {
      console.log("hello2", this);
    };
  }
  new D().hello1();
  new D().hello2();
```
```react
  //get set
    class A {
      _name = "no name";

      get name() {
        return this._name + "SSS";
      }
      set name(value) {
        this._name = value + "111";
      }
    }

    const a = new A();
    console.log(a);
    a.name = "Mark";
    console.log(a); //Mark111

    console.log(a.name); // Mark111SSS
    console.log(a._name); //Mark 111
    
    //readonly set함수를 없앰
    class B {
      _name = "no name";

      get name() {
        return this._name + "SSS";
      }
    }
    const b = new B();
    console.log(b);
    b.name = "Mark";
    console.log(b);
```
```react
    //static 변수, 함수
      class C {
        static age = 37;
        static hello() {
          console.log(C.age);
        }
      }
      console.log(C, C.age);
      C.hello();

      class D {
        age = 37;
        static hello() {
          console.log(this.age);
        }
      }
      console.log(D, D.age);
      D.hello();

      //이름 자체가 클래스가 됨
      class E {
        static name = "this is not name E class";
      }
      console.log(E); //[class this is not name E class] { name: 'this is not name E class' }
```
```react
  //상속 기본
    class Parent {
      name = "Lee";

      hello() {
        console.log("hello", this.name);
      }
    }

    class Child extends Parent {}

    const p = new Parent();
    const c = new Child();
    console.log(p, c);

    c.hello(); //hello Lee
    c.name = "Anna";
    c.hello(); //hello Anna
```
```react
  //변수, 함수 추가 및 오버라이딩

    class Parent {
      name = "Lee";

      hello() {
        console.log("hello", this.name);
      }
    }

    class Child extends Parent {
      age = 37;

      hello() {
        console.log("hello", this.name, this.age);
      }
    }

    const p = new Parent();
    const c = new Child();
    c.hello(); //hello Lee 37
    c.name = "Mark";
    c.hello(); //hello Mark 37

```
```react
  //super 클래스의 상속 생성자 함수 변경

    class Parent {
      name;

      constructor(name) {
        this.name = name;
      }
      hello() {
        console.log("hello", this.name);
      }
    }

    class Child extends Parent {
      age;

      constructor(name, age) {
        super(name); //부모에서 네임을 가지고 옴
        this.age = age;
      }
      hello() {
        console.log("hello", this.name, this.age);
      }
    }
    const p = new Parent("Mark");
    const c = new Child("Mark", 37);

    console.log(p, c);
    c.hello();

```
```react
  // static 상속
    class Parent {
      static age = 37;
    }

    class Child extends Parent {}

    console.log(Parent.age, Child.age);
```

### Promise
  - 비동기 작업이 맞이할 미래의완료 또는 실패와 그 결과 값을 나타냄
  - ![image](https://user-images.githubusercontent.com/80936709/127463341-70b4cd51-3f9a-4deb-8a7a-1794ad50186d.png)
  - 조금더 효율적으로 로직 구성하기
  - ![image](https://user-images.githubusercontent.com/80936709/127464392-b49ed236-d940-474e-b399-1ccdbccc2dea.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127465206-1ee574ec-0d20-438b-b70a-b413e400a1db.png)
    - 전송 실패했을 경우 성공했을 경우를 나눠서 보기 위한 것 / 인자를 전달 할 경우에는 message 처럼 사용하면 됨
    - ![image](https://user-images.githubusercontent.com/80936709/127465849-28aedb43-5bc6-4d3d-9d15-4d4bf2622d7a.png)
    - ![image](https://user-images.githubusercontent.com/80936709/127469758-8c4fd206-4f26-4583-8a04-1ea02e2170f9.png)
    - ![image](https://user-images.githubusercontent.com/80936709/127471647-caa3df63-cab5-4492-adde-ffc093d1eeba.png)
    - ![image](https://user-images.githubusercontent.com/80936709/127472450-c11e687e-c6ae-454e-905d-37008b86d6af.png)
    - ![image](https://user-images.githubusercontent.com/80936709/127472703-607bb267-f7be-47f1-93e8-a78a4a72e659.png)

### async -await
  - ![image](https://user-images.githubusercontent.com/80936709/127477453-f98885ed-496c-40fc-b340-defd75de83c1.png)


