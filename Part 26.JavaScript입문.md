# Part 26.JavaScript입문

### 변수와 상수
 - 특정이름의 특정값을 담을 때 사용함
 - 변수(let) : 바뀔 수 있는 값을 의미함 / 변수 선언시 같은 이름으로 선언할 수 없음 한번만 사용 가능함
 - 상수(const) : 한 번 값을 설정하면 변경할 수 없음
 - 타입(type) 
  - string(문자열)
  - boolean(true,false)
  - null:진짜 없다 ex)친구가 없음 // undefined:아직 정해지지 않았다 ex) 범인은 있지만 아직 누구인지 모르는 것

### 연산자
  - a =1
  - 대입연산자(=) / a+=2 => a+2 = 3
  - 산술연산자 : 사칙연산
    - a++ /1 ++a /2
  - 논리연산자 : NOT(!) AND(&&) OR(||) 우선순위 오른쪽 > 왼쪽
  - 두 값을 비교할 경우에는 === 로 사용함 // == type을 비교하지 않음 // 값이 같지 않을 경우 !==
  - 크고 작은거를 비교할 경우에는 < > 사용하기 <= >= equal사인이 뒤에 온다는거를 주의

### 조건문
  - ![image](https://user-images.githubusercontent.com/80936709/127819613-04fdfc50-4265-4c72-8983-ca5b3fadcdfe.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127819962-18b7a457-166a-44d6-b676-c0d6d01668ba.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127820151-03cd6a9a-f321-4d1f-9646-cde1ef5fc882.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127820789-a2cb6070-023b-44c7-8fa5-63c3cbc64dcd.png)
    - case 값 이렇게 넣어주고 break를 항상 사용하고 어디에도 해당되지 못할 경우에는 default로 나오게 됨

### 함수
  - ![image](https://user-images.githubusercontent.com/80936709/127823715-061cb6aa-45f5-4c27-aa05-989a417ba6c6.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127824423-710c0222-9013-41d4-a994-0e0ff28b06d0.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127825071-920f77ca-04af-4b22-ac59-0566d0267374.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127825639-07563ddb-c199-46a8-bc68-b34b1d99a0a7.png)
    - 화살표 함수로 사용할 수 있음

### 객체
  - ![image](https://user-images.githubusercontent.com/80936709/127826500-794605d0-7b24-4999-82f6-57de930fa285.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127831194-db753a93-70b0-487a-bfa8-9afb6079d367.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127831494-2af27fa6-ac35-42c2-b9c7-774d792b639b.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127831613-c6c233dc-5ff2-4cf0-9fb5-e0f982145323.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127832757-109837c4-f972-41c3-9932-140edf6b80ab.png)

### getter setter
  - getter(조회)
    - ![image](https://user-images.githubusercontent.com/80936709/127833645-fcf9bbf5-f364-4ab0-ba42-4e19d5abd12e.png)
  - setter(값 변경)
    - ![image](https://user-images.githubusercontent.com/80936709/127835546-b38304d8-9544-4940-a5ff-bcb595175b32.png)

### 배열 ([])
  - 배열에서의 첫번째 항목은 0에서 부터 시작함
  - 객체 문자열 숫자 넣을 수 있음
  - ![image](https://user-images.githubusercontent.com/80936709/127839452-64e1b3c3-eec8-403d-a0b0-55d9a5ac9c34.png)

### 반복문
  - ![image](https://user-images.githubusercontent.com/80936709/127842567-f2de1071-6906-4e62-8d94-d6747b3ed08d.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127842641-80eca4d1-2876-4bb7-9820-c7256ebf0fb4.png)
  - 이거 대신으로 사용하는 for in
    - ![image](https://user-images.githubusercontent.com/80936709/127842993-57135e2f-9354-4ddc-8833-3450181e7d6c.png)
    
### break, continue
  - ![image](https://user-images.githubusercontent.com/80936709/127843574-4c83f67c-0297-426b-be77-9ac70f63f18e.png)

### 배열 내장함수
  - forEach (값이 다 나오게 하기 위해서)
    - ![image](https://user-images.githubusercontent.com/80936709/127851368-55a8a409-a3d6-48cd-9419-f8f4f5a8a229.png)
  - map (내가 원하는 부분만 출력할수 있고, 간략하게 할수 있음)
    - ![image](https://user-images.githubusercontent.com/80936709/127854168-8de483e5-71f0-449c-9f2f-2acc4b4a9cba.png)
    - ![image](https://user-images.githubusercontent.com/80936709/127854336-1e989705-f1b6-4a29-af5c-2c7bc46d4a06.png)
  - indexOf (내가 원하는 배열을 숫자로 반환함)
    - ![image](https://user-images.githubusercontent.com/80936709/127854669-336c147b-93d1-429b-8b1b-0ac29ff8dbb1.png)
  - findIndex (객체에서 원하는 아이디를 가지고 올 때 번호로 반환함)
  - find(그 배열 자체를 반환함)
    - ![image](https://user-images.githubusercontent.com/80936709/127856097-0144746f-9fbd-4d1d-9a78-81bcc7ce8dee.png)
  - filter (필터를 통해서 그 값만 보여주겠다) / 기존 값이 변경되지 않음
    - ![image](https://user-images.githubusercontent.com/80936709/127939183-dbf8d4b3-2c27-4212-b52d-507738b100b7.png)
  - splice ( 짤린 값만 보여주겠다 / 나머지 값은 그 객체에 있음 / 기존의 값이 변경 됨
    - ![image](https://user-images.githubusercontent.com/80936709/127859170-27e29a8d-7d75-4153-ba87-2270eb554b74.png)
  - slice ( 0,2)
    - ![image](https://user-images.githubusercontent.com/80936709/127859629-d1579ba9-a98d-42fa-9d8e-1999c2a994c5.png)
  - shift(앞에서 부터 빼기) pop(뒤에서 빼기) unshift(앞에 숫자 추가) push(뒤에 숫자 추가) / 기존 배열이 수정 됨
    - ![image](https://user-images.githubusercontent.com/80936709/127935508-6a33171c-3517-4c39-a68e-4c407bb96700.png)
    - ![image](https://user-images.githubusercontent.com/80936709/127935662-cf26d740-af72-45ff-9181-df28e987a6e2.png)
    - ![image](https://user-images.githubusercontent.com/80936709/127935825-795c56ef-82d3-4386-8d9c-22df728be495.png)
    - ![image](https://user-images.githubusercontent.com/80936709/127935875-6bfde48e-a03a-4ab9-92ff-893532879fb6.png)
   - concat(배열을 합쳐줌) / 기존 배열이 수정되지 않음
    - ![image](https://user-images.githubusercontent.com/80936709/127936043-e222d760-5f49-4c42-994e-ddac6103c77e.png)
   - join(배열의 값을 문자열로 합칠 경우 사용함)
    - ![image](https://user-images.githubusercontent.com/80936709/127936334-a857a79a-0c8e-49ed-ae00-6dfc984e9ced.png)
   - reduce(어떤 값을 연산 할 경우에 사용해야 함)
    - ![image](https://user-images.githubusercontent.com/80936709/127936853-3aeacf7d-0e06-4915-afb3-41d60806b448.png)
    - ![image](https://user-images.githubusercontent.com/80936709/127937362-6cb6ec8c-a234-408d-9011-63b022ff5a76.png)
    - ![image](https://user-images.githubusercontent.com/80936709/127937803-89d78672-8f2b-4e11-ab58-e784d15e98e1.png)

### 프로토타입과 클래스
 - 객체 생성자
   - ![image](https://user-images.githubusercontent.com/80936709/127941535-6a9f1822-48e1-4701-bcb7-6958e8d8be4e.png)
 - 객체 생성자를 상속 받음
   - ![image](https://user-images.githubusercontent.com/80936709/127942308-a2b03bf2-02c0-4f4d-833b-9f8efd3ee314.png)
 - 클래스형 상속받기
   - 
 
  


























