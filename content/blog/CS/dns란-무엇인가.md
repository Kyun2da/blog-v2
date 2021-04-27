---
title: DNS란 무엇인가
date: 2021-04-27 18:04:92
category: cs
thumbnail: { thumbnailSrc }
draft: false
---

## DNS란?

DNS란 Domain Name System의 약자이다. 그렇다면 Domain은 무엇일까?

DNS에 대해 자세히 알아보기 전에 도메인이 무엇인지에 대해 알아보도록 하자.

## 도메인 (Domain)

인터넷에 연결되어 있는 장치들은 각각의 장치를 식별할 수 있는 주소를 가지고 있는데 이를 `ip주소`라고 한다.

ip주소는 111.22.33.44 와 같은 숫자형식으로 되어 있는데 이는 사람이 기억하기 매우 어렵다. 이러한 어려움에 따라 도메인이 등장하게 되었는데 도메인은 바로 이러한 숫자들을 우리가 기억하기 쉽게 이름을 부여하는 것을 말한다. 예를들면, www.naver.com이 바로 도메인이다.

그렇다면 도메인 이름을 관리하는 것이 DNS일텐데 도대체 DNS는 어떻게 운영되며 관리되고 있을까?

## DNS에 대해 자세히 들여다 보기

DNS 는 흔히 전화번호부에 비유되는데 이는 `트리 형태`로 구성이 되어 있다.

크게 3단계로 구성되어 있는데 아래 그림과 같이 트리의 형태를 띄는 것을 볼 수 있다.

![도메인 체계](./images/dns.gif)

좀더 자세하게 알고 싶다면 아래의 DNS 구성요소 및 동작원리 동영상을 추천한다.

<iframe width="560" height="315" src="https://www.youtube.com/embed/fINh76spaiI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 참고

- [도메인 네임 시스템 - 위키백과](https://ko.wikipedia.org/wiki/%EB%8F%84%EB%A9%94%EC%9D%B8_%EB%84%A4%EC%9E%84_%EC%8B%9C%EC%8A%A4%ED%85%9C)
- [도메인 - 생활코딩](https://opentutorials.org/course/228/1450)
- [DNS - 한국 인터넷 정보센터](https://xn--3e0bx5euxnjje69i70af08bea817g.xn--3e0b707e/jsp/resources/dns/dnsInfo.jsp)
- [DNS구성요소 및 동작원리 - 유튜브](https://www.youtube.com/watch?v=fINh76spaiI)
