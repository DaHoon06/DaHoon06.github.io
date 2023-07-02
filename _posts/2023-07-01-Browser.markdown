---
layout: post
title: Browser
date: 2023-07-01 00:00:00 +0200
image: banner/network.png
tags: [Browser]
categories: network
---

#### 클라이언트 요청 구조

#### Web Server

```text
💡 클라이언트가 웹 브라우저에 어떠한 페이지를 요청 하였을 때 웹 서버에서 그 요청을 받아 정적 컨텐츠를 제공하는 서버 - Apache / Nginx

HTTP 또는 HTTPS 요청이 왔을 때 파일 내용을 그대로 응답만 해주는 서버 `[html, css, js 등]`   
파일 확장자에 따라 연결된 다른 서버 `WAS`로 연결만 해주는 서버이다.

웹 서버가 동적 컨텐츠를 요청 받았을 경우 `WAS`에 요청을 넘겨 주고 `WAS에서 결과 값을 전달 받아 클라이언트에게 전달해 주는 역할도 한다.
```


#### WAS (Web Application Server)

```text
💡 웹 서버와 웹 컨테이너가 합쳐진 형태 - Tomcat

웹 서버가 단독으로 처리할 수 없는 데이터베이스 조회나 다양한 로직 처리가 필요한 동적 컨텐츠를 제공한다.
```

`nodejs` 환경 또한 정적인 애플리케이션 서버가 되므로 WAS가 된다.

---

### 웹 페이지 동작 원리


