# Part 23.Github 실습

### 오픈그래프와 트위터카드
  - 카카오톡에 링크를 넣으면 그거에 대한 설명이 나오게 됨
```react
    //사이트에 대한 설명을 상세하게 넣은 것
    <!-- http://ogp.me/ -->
    <meta property="og:type" content="website">
    <meta property="og:site_name" content="GitHub">
    <meta property="og:title" content="Build software better, together">
    <meta property="og:description" content="GitHub clone coding / GitHub is where people build software. More than 31 million people use GitHub to discover, fork, and contribute to over 100 million projects.">
    <meta property="og:image" content="img/logo__github.png">
    <meta property="og:url" content="https://github.com">
    
    //트위터에서 보여주는 정보라고 생각하면 됨
    <!-- https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started.html -->
    <meta property="twitter:card" content="summary">
    <meta property="twitter:site" content="GitHub">
    <meta property="twitter:title" content="Build software better, together">
    <meta property="twitter:description" content="GitHub clone coding / GitHub is where people build software. More than 31 million people use GitHub to discover, fork, and contribute to over 100 million projects.">
    <meta property="twitter:image" content="img/logo__github.png">
    <meta property="twitter:url" content="https://github.com">
```
### 파비콘
  - 사이트를 대표하는 아이콘
  -  google font : 폰트 설정
  -  작명할 경우
    -  __ : ~의 일부분 ex) container__item
    -  -- : ~의 상태 ex) btn--danger
    -  - : 일반적인 작명

### 전역 스타일
```react
  /* Vendor Prefix (브라우저 업체별 접두사) */
  .input--text::-webkit-input-placeholder {color:red;}
  .input--text::-ms-input-placeholder {color:red;}
  .input--text::-moz-input-placeholder {color:red;}
  .input--text::-o-input-placeholder {color:red;}
```
