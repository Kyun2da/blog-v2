---
title: Jekyll 에서 Gatsby로 블로그 이동
date: 2021-02-04 02:02:05
category: Essay
thumbnail: { thumbnailSrc }
draft: false
---

## 1. 블로그를 바꾸게 된 계기

여태까지 [지킬을 이용한 블로그](https://kyun2da.github.io/)를 사용하고 있었다.
루비라는 언어를 잘 알지 못해 블로그를 커스터마이징 하는 것이 매우 까다로웠고, 내가 조금이라도 알고있는
리액트로 개발된 Gatsby로 이동하겠다는 생각을 막연하게 갖고 있었다. 그래서 지금같이 시간이 날때 아니면 블로그를 이동할 기회가 흔치 않을 것 같아서 이번 기회에 블로그를 이전하게 되었다.

## 2. Jekyll 과 Gatsby 의 차이점?

[Gatsby vs Jekyll vs Hugo](https://www.gatsbyjs.com/features/jamstack/gatsby-vs-jekyll-vs-hugo) Gatsby가 광고하고 있는 차이점들을 나열해놓은 페이지에 따르면 모든 면에서 Gatsby가 성능을 압도하고 있는 것을 볼 수 있다. ~~물론 갯츠비가 만들어 놓은 사이트라 주관은 들어갔을 것 같다 ㅋㅋ~~

또한, Gatsby.js 는 `리액트`, Jekyll은 Ruby를 사용해서 나에게도 훨씬더 커스터마이징이 가능해 보였다.

그리고 이걸 쓰면서 느끼는 거지만 빌드 시간이 진짜 차원이 다르다. 거의 한 10배는 차이나서 블로그 쓰는데 시간을 훨씬 줄일 수 있을 것 같다.👍

## 3. 좋은 테마 : Gatsby-starter-bee의 발견, 그리고 Netlify

Gatsby를 둘러보던 중에 [Gatsby-starter-bee](https://github.com/JaeYeopHan/gatsby-starter-bee)를 발견하였다. 한재엽님이 개발하신 이 템플릿은 이미 많은 사람들에게 널리 쓰이고 있었고 나도 이 UI가 상당히 마음에 들어서 채택하게 되었다.

이번에 블로그를 호스팅하면서 [Netlify](https://www.netlify.com/)를 발견하게 되었는데 진짜 이 서비스는 정적 페이지를 호스팅하는데에 더할 나위 없는 것 같다. 물론 현재 Github Pages로 충분히 정적 페이지를 호스팅할 수 있지만, Netlify가 훨씬 쉽고 많은 기능들이 있어 Netlify를 사용하기로 했다. 나중에는 Netlify 기능도 알아보면서 포스팅을 해보면 좋을 것 같다.

## 4. 앞으로 더 커스터마이징 하고 싶은 것들?

### TOC

`TOC(Table Of Contents)`를 개발해서 데스크탑 같은 큰 화면에서는 목차를 한눈에 확인할 수 있게 하고 싶다.

### 카테고리

현재 카테고리 가시화가 잘 되어 있지 않는 것 같다. 목차쪽에서 카테고리를 좀더 자세히 보여주거나 포스트쪽에서도 제목 밑에 카테고리를 보여주면 좋을 것 같다.

### 다크모드 위치

다크모드 위치가 별로 마음에 안드는데 위치를 오른쪽 하단에 놓게하는 것도 좋은 것같다. 추가로 위로 한번에 올라가는 기능도 있으면 좋을듯!

### 방문자 수

몇명이 읽었는지 간단하게 보여주는 텍스트를 구현하면 좋을 것 같다. 예전에는 hit이라는걸 썼었는데 좀 UI랑 안맞기도 해서 Gatsby에서 구현하는 방법이 있으면 찾아보면 좋을 것 같다.

### 구독 기능?

이게 정적페이지에서 될런지는 모르겠지만 사람들이 내 블로그를 읽고 싶다면 이메일 주소를 추가해서 내가 글을 쓰면 이메일을 보내는 기능이 있으면 좋을 것 같다.

### 검색 기능

검색 기능은 내가 쓰기 위해서라도 무조건 만드는 게 좋을 듯 하다.

### 참고할 블로그 목록

- [wDever.dev](https://wdever.dev/)
- [ha-young.github.io](https://ha-young.github.io/blog)
- [https://blueshw.github.io/2020/05/30/table-of-contents/](https://blueshw.github.io/2020/05/30/table-of-contents/)
- [https://jaeseokim.github.io/](https://jaeseokim.github.io/)

### 검색엔진 최적화

지금 검색엔진이 최적화 되어있는지 안되어있는지 잘 모르겠는데 최적화 방법들을 찾아보며 시도해 봐야겠다.

## 5. 앞으로 어떻게 블로그의 방향성

사실 예전부터 블로그를 하긴 했지만 귀찮기도 하고 번거롭기도 해서 자주 포스팅을 하지는 않았다.

근데 개발자라는 직업상 블로깅이 나름의 커리어를 어필할 수 있는 측면도 있고, 기록을 남겨두면 내가 또 다시 참고할때도 있어서 꼭 필요하다는 것을 느꼈다.

그래서 꼭 새로운 기술을 배우면 포스팅하고 앞으로는 내 개인적인 공간인 만큼 잡다한 기록도 많이 해두려고 한다.😃

앞으로 재미있게 블로그를 운영해봐야겠다~
