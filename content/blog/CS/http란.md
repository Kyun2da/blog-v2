---
title: http란
date: 2021-04-28 18:04:43
category: cs
thumbnail: { thumbnailSrc }
draft: false
---

![http](./images/http.png)

## 시작하기 전에

HTTP에 대한 모든 내용을 이 하나의 문서로만 다루기는 매우 내용이 많기 때문에 나중에 시리즈로 다루거나 하도록 하고 여기서는 HTTP가 무엇인지, 대표적인 특성들은 무엇인지에 대해서만 다뤄보도록 하겠다.

## HTTP란?

HTTP란 `Hyper Text Transfer Protocol`의 약자로 말 그대로 하이퍼 텍스트를 전송하는 프로토콜이다.

팀 버너스 리와 그의 팀은 CERN에서 HTML을 전송하기 위해 HTTP 라는 프로토콜을 발명하였다.

HTTP는 클라이언트와 서버 사이에 이루어지는 요청/응답 프로토콜이다. 1990년대 초에 설계된 HTTP는 거듭하여 진화해온 확장 프로토콜이며, `애플리케이션 계층의 프로토콜`이다. 보통 TCP혹은 암호화된 연결의 TLS를 통해 전송된다.

## HTTP의 특징

1. `HTTP는 간단하다` : HTTP는 사람이 읽을 수 있도록 간단하게 고안되었다. HTTP/2에서 더 복잡해지기는 했지만 여전히 HTTP 메시지를 프레임별로 캡슐화하여 간결함을 유지하였다.
2. `확장 가능하다` : 클라이언트와 서버가 새로운 헤더의 시맨틱에 대해서만 합의한다면, 언제든지 새로운 기능을 추가할 수 있다.
3. `무상태(Stateless)`: HTTP는 상태를 저장하지 않는다. 즉, 통신간의 연결 상태 처리나, 정보를 저장할 필요가 없기 때문에 서버 디자인이 간단해진다는 장점이 있다. 만약 저장이 필요한 경우에는 쿠키나 세션을 활용해 정보를 저장할 수 있다.
4. `비연결성(Connectionless)`: HTTP는 클라이언트와 서버가 한 번 연결을 맺은 후, 클라이언트의 요청에 대해 서버가 응답을 마치면 맺었던 연결을 끊어버리는 성질을 말한다. 이러한 특징의 장점은 컴퓨터마다 매번 연결을 유지할 필요가 없기 때문에 리소스를 줄일 수 있어 더 많은 연결을 그때그때 수행할 수 있다는 장점이 있다. 하지만 연결 해제를 매번 해주어야 때문에 이에 대한 오버헤드가 일어난다는 단점또한 가지고 있다.

## HTTP의 흐름

1. TCP 연결을 연다.
2. HTTP 메시지를 전송한다.
3. 서버에 의해 전송된 응답을 읽는다.
4. 연결을 닫거나 다른 요청들을 위해 재사용한다.

## 기본적인 HTTP 메시지 형식

### 요청

![http 요청 예시](./images/http_request.png)

1. http 메서드
2. 리소스의 경로
3. http 프로토콜 버전
4. 헤더
5. body

### 응답

![http응답 예시](./images/http_response.png)

1. http 프로토콜 버전
2. 상태 코드
3. 상태 메시지
4. http 헤더
5. body

## 마치며

HTTP란 무엇이고 HTTP의 특징들에 대해 간단하게 알아보았다. 앞으로 HTTP/1과 HTTP/2의 비교, HTTP와 HTTPS의 차이, HTTP 헤더와 상태코드에 대해서 좀더 자세하게 포스팅 해보도록 하겠다.

## 참고

- [HTTP - 위키백과](https://ko.wikipedia.org/wiki/HTTP)
- [HTTP - MDN](https://developer.mozilla.org/ko/docs/Web/HTTP)
