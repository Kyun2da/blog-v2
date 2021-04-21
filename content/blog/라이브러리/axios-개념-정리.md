---
title: axios 개념 정리
date: 2021-04-21 12:04:50
category: 라이브러리
thumbnail: { thumbnailSrc }
draft: false
---

![axios](./images/axios.svg)

## 이 글을 쓰게 된 이유

개인적으로 axios를 쓰고는 있었지만 확실하게 개념확립이 안되어 있는 것 같아 글을 쓰기로 했다.

이 글은 [axios](https://github.com/axios/axios)에 대한 간단한 개념 정리이며, 더 자세한 개념을 알고 싶다면 [axios 공식문서](https://axios-http.com/)나 [axios 러닝 가이드 번역 사이트](https://xn--xy1bk56a.run/axios/)를 추천한다.

## axios란?

공식 문서에 따르면 axios의 정의는 다음과 같다.

> Axios는 브라우저, Node.js를 위한 Promise API를 활용하는 HTTP 비동기 통신 라이브러리입니다

일종의 자바스크립트에 내장되어 있는 fetch api와 유사한 기능을 하지만 차이점이 몇가지 있다. 그렇다면 axios의 장단점을 알아보기 위해 그 차이를 비교해보도록 하자.

## axios vs fetch

아래의 표는 [Geeks for Geeks글](https://www.geeksforgeeks.org/difference-between-fetch-and-axios-js-for-making-http-requests/)을 참조하였다.

| axios                                           | fetch                                                          |
| ----------------------------------------------- | -------------------------------------------------------------- |
| 요청 객체에 url이 있다.                         | 요청 객체에 url이 없다.                                        |
| 써드파티 라이브러리로 설치가 필요               | 현대 브라우저에 빌트인이라 설치 필요 없음                      |
| XSRF 보호를 해준다.                             | 별도 보호 없음                                                 |
| data 속성을 사용                                | body 속성을 사용                                               |
| data는 object를 포함한다                        | body는 문자열화 되어있다                                       |
| status가 200이고 statusText가 'OK'이면 성공이다 | 응답객체가 ok 속성을 포함하면 성공이다                         |
| 자동으로 JSON데이터 형식으로 변환된다           | .json()메서드를 사용해야 한다.                                 |
| 요청을 취소할 수 있고 타임아웃을 걸 수 있다.    | 해당 기능 존재 하지않음                                        |
| HTTP 요청을 가로챌수 있음                       | 기본적으로 제공하지 않음                                       |
| download진행에 대해 기본적인 지원을 함          | 지원하지 않음                                                  |
| 좀더 많은 브라우저에 지원됨                     | Chrome 42+, Firefox 39+, Edge 14+, and Safari 10.1+이상에 지원 |

위와 같은 표를 보았을 때 axios는 `별도의 설치가 필요하다는 단점`이 있지만 그것을 커버할 만한 fetch 보다 `많은 기능 지원과 문법이 조금이나마 간소화 된다는 장점`이 있다는 것을 볼 수 있다.

그렇다면 간단하게 사용할때는 fetch를 쓰고, 이외의 확장성을 염두해봤을 땐 axios를 쓰면 좋을 것 같다.

이제, axios 기본적인 사용법에 대해 살펴보도록 하자.

## axios 기본 사용법

사실 위의 [공식문서 번역](https://xn--xy1bk56a.run/axios/)을 쭉 읽어보면 기본 사용법 뿐만 아니라 다양한 config 설정등이 나와있어서 문제없이 사용할 수 있지만 여기서도 간단하게 한번 짚고 넘어가보자 한다.

```js
const axios = require('axios')

// ID로 사용자 요청
axios
  .get('/user?ID=12345')
  // 응답(성공)
  .then(function(response) {
    console.log(response)
  })
  // 응답(실패)
  .catch(function(error) {
    console.log(error)
  })
  // 응답(항상 실행)
  .then(function() {
    // ...
  })
```

위는 기본 코드의 사용법이고 최근에는 아래와 같이 async await를 같이 사용해서 좀더 보기 좋게 쓰기도 한다.

```js
async function getUser() {
  try {
    const response = await axios.get('/user?ID=12345')
    console.log(response)
  } catch (error) {
    console.error(error)
  }
}
```

인스턴스를 하나 생성해서 axios 기본 세팅을 할 수도 있다.

```js
const instance = axios.create({
  baseURL: 'https://some-domain.com/api/',
  headers: { 'X-Custom-Header': 'foobar' },
  timeout: 1000,
})
```

이정도가 기본적으로 사용하는 방법인 것 같고 이제 좀 더 자세한 config정보와 응답 스키마 종류에 대해서 알아보도록 하자.

## config option과 응답 스키마

config 옵션은 너무 길어서 따로 [공식문서의 url](https://xn--xy1bk56a.run/axios/guide/api.html#%EA%B5%AC%EC%84%B1-%EC%98%B5%EC%85%98)을 참조하도록 하겠다.

응답 스키마는 데이터를 받아올 때 알아야 하는데 다음과 같이 6종류가 있다.

```js
{
  // `data`는 서버가 제공한 응답(데이터)입니다.
  data: {},

  // `status`는 서버 응답의 HTTP 상태 코드입니다.
  status: 200,

  // `statusText`는 서버 응답으로 부터의 HTTP 상태 메시지입니다.
  statusText: 'OK',

  // `headers` 서버가 응답 한 헤더는 모든 헤더 이름이 소문자로 제공됩니다.
  headers: {},

  // `config`는 요청에 대해 `axios`에 설정된 구성(config)입니다.
  config: {},

  // `request`는 응답을 생성한 요청입니다.
  // 브라우저: XMLHttpRequest 인스턴스
  // Node.js: ClientRequest 인스턴스(리디렉션)
  request: {}
}
```

`then`을 사용하면 다음과 같이 응답을 받을 수 있다.

```js
axios.get('/user/12345').then(function(response) {
  console.log(response.data)
  console.log(response.status)
  console.log(response.statusText)
  console.log(response.headers)
  console.log(response.config)
})
```

## 마치며

평소에 axios를 쓰다가 fetch가 있는데 왜 굳이 axios를 쓰지? 하는 생각이 많이 들었었는데 이번 기회에 axios를 공부하면서 궁금점을 조금이나마 해결할 수 있었다.

단순히 라이브러리가 유명해서 쓰는 것이 아닌 왜 이 라이브러리를 쓰는지 이 라이브러리의 장점은 꼭 알아야겠다고 생각해서 앞으로도 라이브러리를 하나하나 간단하게라도 정리해볼까 한다.

## 참고

- [axios github](https://github.com/axios/axios)
- [axios official document](https://axios-http.com/)
- [axios 공식 문서 번역](https://xn--xy1bk56a.run/axios/)
- [axios vs fetch Geeks for Geeks](https://www.geeksforgeeks.org/difference-between-fetch-and-axios-js-for-making-http-requests/)
