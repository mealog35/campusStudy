# Part 28.비동기 처리

### 동기식 처리 / 비동기식 처리
  - ![image](https://user-images.githubusercontent.com/80936709/127956737-a9aaf59e-c13f-4e04-a69e-d71daf367839.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127957529-c53d0c02-84ec-4fe3-8300-4fea035a7458.png)

### Promise
  - 비동기 작업을 편하게 하기 위해서 도입된 함수
  - ![image](https://user-images.githubusercontent.com/80936709/127958031-4966746c-1587-44ab-b9db-48ee285df007.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127958371-34b579e7-7064-4616-bfc9-4370c231bf2a.png)

### await / async
  - ![image](https://user-images.githubusercontent.com/80936709/127959632-e3bb52d9-4786-448e-9200-7d9e622be1d8.png)
  - ![image](https://user-images.githubusercontent.com/80936709/127959690-5b6f5651-e17f-4616-b953-0b3928478e1f.png)

### promise.all / promise.race (가장 빨리 끝난것만 나타냄)
  - ![image](https://user-images.githubusercontent.com/80936709/127960483-2bfc9fb2-5fcf-4b4f-9c19-8c0bf6867451.png)


```react
import axios from "axios";

const error = {
  data: {
    code: "EREGUEST",
    originalError: "error",
  },
};

//서명 조회
export const getSignAPI = (employeeNo) =>
  axios
    .get(`${process.env.REACT_APP_API_URL}/signature/${employeeNo}`, {
      // responseType: "arraybuffer",
    })
    .then((res) => {
      // console.log("서명조회 성공", res);
      // const base64 = Buffer.from(res.data, "utf8").toString("base64");
      // console.log("getSignAPI - base64", "data:;base64," + base64);
      return res.data;
    })
    .catch((e) => {
      // console.log("서명조회 실패", e);
      return error;
    });

//서명 등록
export const postSignAPI = (employeeNo, body) =>
  axios
    .post(`${process.env.REACT_APP_API_URL}/signature/${employeeNo}`, body)
    .then((res) => {
      // console.log("서명등록 성공", res);
      return res.data;
    })
    .catch((e) => {
      // console.log("서명등록 실패", e);
      return error;
    });

//서명 수정
export const putSignAPI = (employeeNo, body) =>
  axios
    .put(`${process.env.REACT_APP_API_URL}/signature/${employeeNo}`, body)
    .then((res) => {
      // console.log("서명수정 성공", res);
      return res.data;
    })
    .catch((e) => {
      // console.log("서명수정 실패", e);
      return error;
    });

//서명 삭제
export const deleteSignAPI = (employeeNo) =>
  axios
    .delete(`${process.env.REACT_APP_API_URL}/signature/${employeeNo}`)
    .then((res) => {
      // console.log("서명삭제 성공", res);
      return res.data;
    })
    .catch((e) => {
      // console.log("서명삭제 실패", e);
      return error;
    });

```


