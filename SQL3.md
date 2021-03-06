### 3장 SQL Server 전체 운영 실습

#### 3.1 요구사항 분석과 시스템 설계와 모델링
- 분석, 설계, 구현, 시험, 유지보수 (총 5단계)
### 3.1.2 데이터베이스모델링과 필수 용어

![image](https://user-images.githubusercontent.com/80936709/152935980-9b19a47c-53b9-4b94-8da3-0fa8a481e056.png)

### SQL 실습
- ![image](https://user-images.githubusercontent.com/80936709/152942040-fe39969a-5458-4307-b519-fcd399f6a96d.png)
- ![image](https://user-images.githubusercontent.com/80936709/152942161-277d82eb-c043-480d-84a1-aeec3477099f.png) (그 해당 테이블에만 만들 것이다)
- ![image](https://user-images.githubusercontent.com/80936709/152942255-86cae706-43f1-4c59-b460-bad659e7e554.png) (드래그 한 부분만 결과물로 보여줌)

### 테이블 외의 데이터베이스개체의 활용
- 데이터베이스 안에 '테이블'만 표현되어 있음
- 테이블 외에 다른 중요한 데이터베이스 개체로는 인덱스, 저장 프로시저, 함수, 트리거, 커서 등이 있음

#### 인덱스
- 대부분의 책의 제일 뒤에 붙어 있는 찾아보기 또는 색인과 같은 개념이다
- ![image](https://user-images.githubusercontent.com/80936709/152957905-d0dc9791-cc2b-4324-a020-ca52b9232357.png)
- ![image](https://user-images.githubusercontent.com/80936709/152957685-76b06e8e-a118-4c83-8806-f1dc07a4defc.png)

#### 뷰
- 가상의 테이블
- 진짜 테이블에 링크 된 개념

### 저장 프로시저
- SQL Sever에서 제공해주는 프로그래밍 기능

### 트리거
- INSERT, UPDATE, DELETE 할 경우 동작함
- 회원 테이블에 삭제작업이 일어날 경우 삭제되기 전에 미리 다른 곳에 삭제될 데이터를 자동으로 저장해주는 기능이 있음
- ![image](https://user-images.githubusercontent.com/80936709/153104625-d1849fd2-7d16-428e-8cef-d3cfd62f4102.png)

### 데이터베이스 백업 및 관리
- 백업 : 현재의 데이터베이스를 다른 매체에 보관하는 작업
- 복원 : 데이터베이스에 문제가 발생했을 때 다른 매체에 백업된 데이터를 이용해서 원상태로 돌려놓는 작업을 말함
