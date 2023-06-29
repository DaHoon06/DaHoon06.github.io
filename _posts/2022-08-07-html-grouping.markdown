---
layout: post
title: HTML Grouping Element
date: 2022-08-07 00:00:00 +0200
image: html.png
tags: [HTML, SemanticTag]
categories: html
---

<nav>
    <ol>
        <h5>목차</h5>
        <li style="color: #9b9b9b">
            <a href="#p" style="color: #9b9b9b;">p 요소</a>
        </li> 
        <li style="color: #9b9b9b">
            <a href="#Blockquote" style="color: #9b9b9b">Blockquote 요소</a>
        </li> 
        <li style="color: #9b9b9b">
            <a href="#menu" style="color: #9b9b9b">ol, ul, menu, li  요소</a>
        </li> 
        <li style="color: #9b9b9b">
            <a href="#dl" style="color: #9b9b9b">dl, dt, dd 요소</a>
        </li> 
        <li style="color: #9b9b9b">
            <a href="#figure" style="color: #9b9b9b">figure, figcaption 요소</a>
        </li> 
        <li style="color: #9b9b9b">
            <a href="#main" style="color: #9b9b9b">main 요소</a>
        </li>
        <li>
            <a href="#div">div 요소</a>
        </li>
    </ol>
</nav>

<br />

Grouping 요소는 말그대로 요소들의 그룹을 짓는 요소를 의미합니다.

> <span id="p">p</span>

***

```p``` 요소는 Paragraph(문단)을 의미합니다.       
```p``` 는 블럭 요소로써 사용시에 한줄 전체를 사용하게 됩니다.

{% highlight html %}
<h1>HTML Grouping Content - p</h1>
<p>첫번째 문단</p>
<p>두번째 문단</p>
<p>세번째 문단</p>
{% endhighlight %}      

<br />

> <span id="Blockquote">Blockquote</span>

***

block quotation 을 의미합니다.        
```blockquote``` 요소를 사용했다라는건 사용된 문구가 인용문임을 나타냅니다.       
cite 속성을 통해서 인용문의 출처를 나타낼 수 있습니다.       

```cite``` 속성이 아닌 태그로써 표현할 수도 있습니다.

{% highlight html %}
<blockquote cite="URL">
    <p>blockquote 내부에 사용된 텍스트는 인용문임을 나타냅니다.</p>
    <p>HTML은 문서를 표현하기 위해 만들어진 언어지만, 현재는 웹 애플리케이션에서도 활용됩니다.</p>
    <!-- 출처 표시 -->
    <cite>MDN</cite>
</blockquote>
{% endhighlight %}

<br />

> <span id="menu">ol, ul, menu, li</span>

***

```ul``` 요소는 **정렬되지 않은 목록 (unordered list)**, 순서가 중요하지 않는 목록을 나타낼 때 사용됩니다.        

순서가 중요하지 않은 리스트: 추천 검색어, 등

```ol``` 요소는 **정렬된 목록 (ordered list)**, 순서가 중요한 목록을 나타낼 때 사용됩니다.       

순서가 중요한 리스트: 목차, 실시간 검색어 등 조건에 따라 순서가 변동되는 것


```li``` 요소는 목록의 아이템 **(list items)**을 나타냅니다.       

```li``` 는 항목을 나타냄으로 반드시 ```ul``` ```ol``` 내부에 사용되야 합니다.

{% highlight html %}
<h1>실시간 검색어</h1>
<ol>
    <li>HTML</li>
    <li>TypeScript</li>
    <li>Java</li>
</ol>
<h1>추천 검색어</h1>
<ul>
    <li>순대국</li>
    <li>햄버거</li>
    <li>파스타</li>
</ul>
{% endhighlight %}

```menu``` 요소는 ```ul``` 요소의 대체 요소로써, 비정렬형 리스트입니다.       
차이점은 ```menu``` 요소의 ```li```는 각각의 항목에 사용자가 활성화할 수 있는 **링크** 또는 **명령** 을 나타냅니다.

{% highlight html %}
<menu type="context" id="dropdown-menu">
  <li>
    <button>복사</button>
  </li>
  <li>
    <button>잘라내기</button>
  </li>
  <li>
    <button>붙여넣기</button>
  </li>
</menu>

{% endhighlight %}

<br />

> <span id="dl">dl, dt, dd </span>

***

```dl``` 요소는 용어```dl```와 용어에 대한 정의```dt``` 그룹을 목록으로 감싸는 **정의 목록(description list)** 태그 입니다.     
Key-Value 형태로 정보를 제공할 때 ```dl``` 요소를 활용할 수 있습니다.        

```dl``` 요소의 직계요소로는 ```dt``` ```dl``` ```div``` 만 사용할 수 있습니다.

<small style="color: gray;">( ```dl``` 요소 내에서 특정 요소들을 그룹해야하는 경우에 한하여 ```div``` 요소를 활용할 수 있습니다. )</small>

```dt``` 요소는 정의 또는 설명 목록의 정의하는 용어 (description term), **Key 값을 나타낼 때** 사용됩니다.       
보통 ```dt``` 요소 뒤에 ```dd``` 요소가 오게 되는데, 여러 개의 ```dt``` 요소를 연속으로 배치하고 하나의 ```dd``` 요소로 앞의 모든 ```dt``` 요소를 서술할 수도 있습니다.

```dd``` 요소는 ```dt``` 요소에 대한 정의나 설명 (description details/date), **Key 값에 대한 Value 값** 을 나타낼 때 사용됩니다.


```dt```와 ```dd```는 무조건 한쌍( 단독 사용 불가능 )으로 사용되어야 합니다.            


{% highlight html %}
<dl>
    <div>
        <dt>마늘</dt>
        <dd>알싸한 맛</dd>
        <dd>다음 마늘 설명입니다.</dd>
    </div>
    <div>
        <dt>상추</dt>
        <dd>쌈 싸먹어</dd>
    </div>
</dl>
{% endhighlight %}

<br />

> <span id="figure">figure, figcaption</span>

***

```figure``` 요소는 콘텐츠의 **부연설명을 하는 콘텐츠를 담을 때 사용**      
```figcaption``` 요소는 콘텐츠의 **부연설명을 하는 콘텐츠를 작성하는 요소**

{% highlight html %}
<p>우주에 관한 내용</p>
<figure>
    <img src="nasa.jpg" alt="nasa" />
    <figcaption>NASA는 미항공우주연구소로 우주 관련 연구를 하는 기관이다.</figcaption>
</figure>
{% endhighlight %}      

```aside``` 요소는 "연관되어 있지만 독립된 콘텐츠"
```figure``` 요소는 "연관된 콘첸츠 그 자체" 즉, **독립성을 보장하지 않아도 무관**
주로 이미지, 동영상, 오디오 등을 활용한 부연설명에 많이 사용됩니다.

<br />

> <span id="main">main</span>

***

```main``` 요소는 ```body``` 내의 주 컨텐츠를 정의할 떄 사용됩니다.        
반드시 문서내에서 단 1개의 ```main``` 요소만 있어야합니다.      
또한 다른 시멘틱 태그들의 자손 요소로써 ```main``` 요소가 사용되어서는 안됩니다.

{% highlight html %}
<main>
    <h1>메인 콘텐츠</h1>
</main>
<main hidden></main>
<main hidden></main>
<main hidden></main>
{% endhighlight %}

예외적으로 한페이지 내에서 여러개의 ```main``` 요소 사용 가능한 경우가 있습니다.      
hidden 속성을 통하여 가리거나 다른 조작을 통해 가려질 경우에 허용되며 활성화 되어있는 main 요소는 언제나 하나여야 합니다.

<br />

> <span id="div">div</span>

***

의미 없이 CSS 등의 목적으로 여러 요소를 Grouping할 때 사용됨        
div 요소는 정말 최후의 수단으로만 활용
