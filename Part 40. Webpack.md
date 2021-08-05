# Part 40. Webpack

### 기본구조
  - entry : 의존성 그래프를 만듦
  - output : 번들 파일에 대한 정보를 설정
  - dependencies : --save
  - devDependencies : --save-dev

### Loader
  - 다양한 모듈들을 입력받아 처리하는 역할
```
  module.exports ={
    module:{
      rules:[loaderr1,loader2]
    }
  }
  ```
  
  ### plugIn
    - 플러그인 객체를 배열 안에 담음
```
  module.exports={
    plugins:[ new plugin({...option}), ...]
  }
