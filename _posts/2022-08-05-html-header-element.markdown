---
layout: post
title: HTML Header Element
date: 2022-08-05 00:00:00 +0200
image: banner/html.jpg
tags: [HTML, SemanticTag]
categories: html
---

<nav>
    <ol>
        <h5>목차</h5>
        <li style="color: #9b9b9b">
            <a href="#head" style="color: #9b9b9b;">head 요소</a>
        </li>
    </ol>
</nav>

<br />

> <span id="head">head</span>

***

```head``` 요소는 meta 요소, 해당 문서 혹은 애플리케이션의 metadata를 담을 때 활용할 수 있습니다.         


{% highlight html %}
<head>
    <!-- meta 요소, 해당 문서 혹은 애플리케이션의 metadata를 담는 요소-->
    <!-- charset, 문자 인코딩을 어떻게 할 것인지 결정 -->
    <!--
        1. UTF-8, 전세계 언어 대부분을 지원
        2. EUC-KR, 한국어와 영문을 지원
        3. DB의 charset과 맞춰서 작업
    -->
    <meta charset="UTF-8">
    <!--
        viewport, 모바일 브라우저(태블릿 PC 포함)에서 화면을 어떻게 노출시킬 지 정하는 메타 데이터
        만약 이 메타 데이터가 없다면 모바일 브라우저에서 화면 렌더링이 이상하게 동작 ( 970px 정도의 넓이을 억지로 scale out 시킨듯한 화면 )
    -->
    <meta name="viewport" content="initial-scale-1, width=device-width">
    <!--
        SEO에 도움을 주는 metadata
        1. description -> 검색 결과의 타이틀과 아래 정보를 나타낸다. (아래 content 정보를 가져와 검색해서 화면에 렌더링)
    -->
    <meta name="description" content="메타데이터 요소에 대한 설명을 다루는 웹페이지입니다.(페이지를 설명하는 문구)">
    <!--
        웹패이지에 대한 설명을 줘도 됨
        만약 없다면 페이지내의 상단 부분을 가져감 ( 메뉴명, 상단 로고 등등 ) 이상하게 긁어오기 때문에 명시해주는게 좋음
    -->
    <!--
        Social Meatadata: Facebook - Open Graph
        Open Graph Protocol: https://ogp.me/
    -->
    <meta property="og:title" content="metadata element">
    <meta property="og:description" content="메타데이터 요소에 대한 설명을 다루는 웹페이지입니다.">
    <!-- 위 description metadata를 설정해줘도 따로 기재해줘야함  -->
    <!-- url을 설정할 경우 페이스북에서 아래 url을 크롤링해감 -->
    <meta property="og:url" content="https://내 URL 설정" >
    <meta property="og:image" content="https://내 URL 설정 ( 단, 이미지를 서버에 업로드 하고 사용하는 것을 권장 )" >

    <!-- Social Metadata: Twitter - Twitter Card -->
    <meta name="twitter:card" content="내용입력~~">
    <meta name="twitter:site" content="유저 아이디 입력">
    <meta name="twitter:title" content="metadata element" >
    <meta name="twitter:description" content="메타데이터 요소에 대한 설명을 다루는 웹페이지 입니다.">
    <meta name="twitter:image" content="이미지 경로" >

    <!-- title: 요소 - 해당 애플리케이션의 제목 -->
    <title>HEADER 내용</title>

    <!-- link 요소 : 외부 문서 or 외부 콘텐츠와 이 콘텐츠를 연결해주는 요소 -->
    <!-- link 요소로 문서를 불러올 경우 http request를 발생시키기 때문에 하나라도 있을 경우 성능 저하를 일으킬 여지가 있다.  -->
    <link rel="stylesheet" href="./style.css">

    <!-- style 요소 : 페이지 내에서 사용하는 CSS를 정의하는 요소 -->
    <!--
        style 요소 내부에 렌더링에 꼭 필요한 스타일만 담아두면 성능 개선에 좋다.
        1. 레이아웃 관련
        2. 폰트 관련
        즉, 전체 구조를 잡는 CSS와 내부 요소를 잡는 CSS
     -->
    <style>
        body {
            font-family: "Apple Braille";
        }
    </style>
</head>
{% endhighlight %}
