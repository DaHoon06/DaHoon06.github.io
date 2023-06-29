---
layout: post
title: HTML Body Element
date: 2022-08-04 15:13:18 +0200
image: banner/html.jpg
tags: [HTML, SemanticTag]
categories: html
---

<nav>
    <ol>
        <h5>목차</h5>
        <li style="color: #9b9b9b">
            <a href="#Body" style="color: #9b9b9b;">Body 요소</a>
        </li> 
        <li style="color: #9b9b9b">
            <a href="#heading" style="color: #9b9b9b">heading 요소</a>
        </li> 
        <li style="color: #9b9b9b">
            <a href="#grouping" style="color: #9b9b9b">article, section, div 요소</a>
        </li> 
        <li style="color: #9b9b9b">
            <a href="#header" style="color: #9b9b9b">header, hgroup, nav 요소</a>
        </li> 
        <li style="color: #9b9b9b">
            <a href="#footer" style="color: #9b9b9b">footer, address 요소</a>
        </li> 
        <li style="color: #9b9b9b">
            <a href="#aside" style="color: #9b9b9b">aside 요소</a>
        </li>
    </ol>
</nav>

<br />

> <span id="body">Body</span>

***

콘텐츠를 담는 HTML 요소     
콘텐츠의 대부분을 차지하고 있어 시맨틱 태그 <small style="color: gray;">(의미있는 태그)</small> 를 잘 활용하는 것이 좋습니다.

<small>
시맨틱 태그를 사용하는 이유
<ul>
    <ol>1. 검색엔진 최적화 (SEO)</ol>
    <ol>2. 쉬운 소스코드 구조화</ol>
    <ol>3. 코드 가독성 향상</ol>
</ul>
즉, 브라우저가 문서를 읽었을 때 정확하게 인식할 수 있도록 해야합니다.
</small> 

<br />

> <span id="heading">heading 요소</span>

***

heading 요소는 ```h1``` ~ ```h6``` 까지의 태그를 의미합니다.       
**숫자가 높을 수록 중요한 제목**을 의미합니다.

heading 요소를 사용하면 **익명 영역(anonymous section)** 이 생기게 됩니다.        
<small>익명 영역(anonymous section) : section 요소를 암묵적으로 포함하고 있다는 의미</small>

{% highlight html %}
<h1>h1 태그 시작 지점 (section 태그의 시작)</h1>
<p>하나의 문단이 존재하네요.</p>
<h6>h6 인거보니 덜 중요한 제목인가보네요. </h6>
<!-- 즉, 여기까지가 하나의 section 영역 -->
<h1>2번째 h1 태그를 만났어요 (이 부분 위까지 section 영역)</h1>
{% endhighlight %}

**h1 요소를 시작된 기준으로 다음 h1 요소를 만날때까지** <u>그 사이에 있는 모든 요소들은 h1 요소 안에 포함된다는 의미</u>가 됩니다.

위 코드를 풀어서 사용해보면 아래와 같습니다.

{% highlight html %}
<h1>h1 요소 시작합니다.</h1>
<p>HTML을 기초부터 다시 공부해봅시다.</p>
<h6>덜 중용한 제목입니다.</h6>

<h1>2 번째 h1 요소가 있네요</h1>

<!-- 위의 코드는 아래 코드와 같습니다.  -->

<section>
    <h1>h1 요소 시작합니다.</h1>
    <p>HTML을 기초부터 다시 공부해봅시다.</p>
    <h6>덜 중용한 제목입니다.</h6>
</section>

<section>
    <h1>2 번째 h1 요소가 있네요</h1>
</section>

<!-- 만약 두번째 h1 태가 아닌 다른 태그가 된다면 하나의 그룹으로 묶이게 됩니다. -->

<section>
    <h1>h1 요소 시작합니다.</h1>
    <p>HTML을 기초부터 다시 공부해봅시다.</p>
    <h6>덜 중용한 제목입니다.</h6>
    <h6>h1 요소가 아닌 h6 요소네요. 그럼 하나로 묶여야죠.</h6>
</section>
{% endhighlight %}

이처럼 heading 요소를 잘 활용하면 전체 페이지의 outline을 잡는데 용이해집니다.

<br />

> <span id="grouping">article, section, div</span>

***

다음으로 시맨틱 태그를 학습하면서 제일 어려웠던 ```article```, ```section```, ```div``` 요소입니다.

어려웠던 아유는 저 요소를 어떨때 활용을 해야하는지 이때 쓰는게 맞는지 알지 못했습니다.       
그러다보니 사이드 프로젝트를 진행하면서 무분별한 ```div``` 남발과 용도에 맞지 않는 ```section```, ```article``` 요소를 사용하였습니다...ㅎㅎㅎ     
<small style="color: gray;">(HTML 부터 다시 공부해보자 라는 계기가 되었습니다.)</small>

```article``` 요소와 ```section``` 요소를 언제 활용할 수 있을지 구분을 지어주는 가장 큰 기준은 **요소의 독립성** 에 있습니다.

```article``` 요소

요소의 내부를 **다른 컴포넌트에서 재사용** 을 할 수 있다면 ```article``` 요소를 활용합니다.        
여기서 주의할 점은 ```article``` 요소로 묶인 컴포넌트 사용할 때 이 컴포넌트를 다른 곳에 사용하였을 때 전혀 어색함이 없어야합니다.        
<small style="color: gray;">(즉, 독립적으로 사용될 수 있어야한다.)</small>

{% highlight html %}
<!-- article 요소의 내부에 또 다른 article로 나눌 수 있는 경우 -->
<!-- 여러개의 article 요소를 활용할 수 있습니다. -->
<article>
    <article>
        <h1>HTML, section 요소</h1>
        <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
        <section>
            <h2>HTML, Article 요소</h2>
            <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
        </section>
        <section>
            <h2>HTML, Aside 요소</h2>
            <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
        </section>
    </article>
    <article>
        <h1>HTML, section 요소</h1>
        <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
        <section>
            <h2>HTML, Article 요소</h2>
            <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
        </section>
        <section>
            <h2>HTML, Aside 요소</h2>
            <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
        </section>
    </article>
</article>
{% endhighlight %}

```article``` 요소 안에 다른 독립적인 영역이 있을 경우 ```article - article``` 과 같이 여러 ```article``` 요소가 존재할 수 있습니다.

```section``` 요소

```section``` 요소의 경우 요소가 쓰인 콘텐츠가 다른 콘텐츠와 연관이 있다면 ```section``` 요소를 활용할 수 있습니다.
<small style="color: gray;">(범용적인 범위 내에서 사용)</small>

{% highlight html %}
<!-- article 내부에 section 요소 활용 -->
<article>
    <h1>HTML, section 요소</h1>
    <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
    <section>
        <h2>HTML, Article 요소</h2>
        <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
    </section>
    <section>
        <h2>HTML, Aside 요소</h2>
        <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
    </section>
</article>
{% endhighlight %}

따라서 ```section``` 요소 안에 ```article``` 요소가 들어가는 것 보다 ```article``` 요소 안에 ```section``` 요소가 들어가는게 위 논리와 맞게 됩니다.

```section``` 요소 안에는 연관된 내용들이 담겨야 하는데 여러 ```article``` 이 존재할 경우 ```article``` 요소는 독립적이기에 안에 내용이 달라질 수 있기 때문에 부자연스러울 수 있습니다.

```article```,```section``` 두 요소를 활용할 때에는 요소 내에 ```heading``` 요소 사용을 권장하고 있습니다.     
<small style="color: gray;">(css를 통하여 heading 요소의 기본값을 지우더라도 heading 요소를 사용해야합니다.)</small>

```div``` 요소

```div``` 요소의 경우에는 ```article```,```section``` 이 두 요소를 활용할 수 없을 때 사용됩니다.        
단순 Grouping 목적으로만 사용되며, 정말 최후의 수단에만 사용하는 것을 권장합니다.      
<small style="color: gray;">(말 그대로 정말 최후의 수단이므로 Semantic Tag를 활용하기 위해서는 사용을 지양해야합니다.)</small>

<br />

> <span id="header">header, hgroup, nav</span>

***

```header``` 요소

특정 콘테츠의 **시작부분을 나타내는 요소** 입니다.

```hgroup``` 요소

**heading 요소를 그룹화 하여 제목 - 부제목 관계를 만드는 요소** 입니다.

{% highlight html %}
<article>
    <nav>
        <a href="#html-section">html section 요소 연결</a>
        <a href="#html-article">html article 요소 연결</a>
    </nav>
    <!-- header는 특정한 콘텐츠의 시작부분을 나타내는 요소 -->
    <header>
        <!-- hgroup 요소는 heading 요소를 그룹화 하여 제묵 - 부제목 관계를 만드는 요소 -->
        <hgroup id="html-section">
            <h1>HTML, section 요소</h1>
            <h2>부제목 영역</h2>
        </hgroup>
        <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
    </header>
    <section id="html-article">
        <h2>HTML, Article 요소</h2>
        <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
    </section>
    <section>
        <h2>HTML, Aside 요소</h2>
        <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
    </section>
</article>
{% endhighlight %}

```nav``` 요소

페이지 내의 **네비게이션 콘텐츠를 담는 요소** (상단, 사이드, 콘텐츠 내부) 입니다.
보통 ```nav``` 요소를 활용할때 메뉴 리스트를 ```ul``` ```li``` 요소를 활요하게 되는데 이는 필수가 아닌 **선택사항** 이므로 다른 요소가 있다면 그 요소를 활용하면 됩니다.

```nav``` 요소의 경우 콘텐츠 요소와 이어줌으로써 좀 더 의미 있는 네비게이션 메뉴를 구성할 수 있습니다.

```a``` 요소의 ```href = ‘#선택자명’``` 에서 #을 붙여 링크를 걸 경우 ```id=’선택자명’``` 와 같이 동일한 선택자명의 위치로 이동해주는 링크를 연결할 수도 있습니다.

{% highlight html %}
<article>
    <nav>
        <a href="#html-section">html section 요소</a>
        <a href="#html-article">html article 요소</a>
    </nav>
    <header>
        <!-- hgroup 요소는 heading 요소를 그룹화 하여 제묵 - 부제목 관계를 만드는 요소 -->
        <hgroup id="html-section">
            <h1>HTML, section 요소</h1>
            <h2>부제목 영역</h2>
        </hgroup>
        <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
    </header>
    <section id="html-article">
        <h2>HTML, Article 요소</h2>
        <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
    </section>
    <section>
        <h2>HTML, Aside 요소</h2>
        <p>이 HTML 문서는 Sections 콘텐츠를 설명하기 위한 문서</p>
    </section>
</article>
{% endhighlight %}

<br />

> <span id="footer">footer, address</span>

***

```footer``` 의 경우 **콘텐츠를 마무리할 때 필요한 요소** 들을 감싸는 요소입니다.      
<small style="color: gray;">(copyright, 작성자 정보, 작성일 등등…)</small>
{% highlight html %}
<footer>
    <p>
        본문 내용~~
        <cite>출처 : <a href="https://www.naver.com">네이버</a></cite>
    </p>
    <!-- address 요소: content information -->
    <address>
        <p>
            작성자: <a href="wwww">전다훈</a>
        </p>
        <p>
            서울시 강남구~~ (전통적인 방법)
        </p>
    </address>
    <!-- publication information: 반드시 address 밖에, footer 안에 -->
    <p>
        <time>2022-08-04</time>
    </p>
</footer>
{% endhighlight %}

<br />

> <span id="aside">aside</span>

***

```aside``` 요소는 핵심 콘텐츠와 관련이 있기는 하지만, 콘텐츠의 전체의 흐름과는 크게 관련 없는 콘텐츠를 표현할 때 사용됩니다. (부가적인 내용을 담는 요소)  
```article``` 요소 내부 또는 외부에서 사용될 수 있습니다.     

```article``` 요소 안쪽에 ```aside``` 요소가 있을 경우, ```article``` 요소의 본문 내용과 관련있는 내용으로 구성되어야하며,     
바깥쪽에서 사용될 경우에는 전체 웹페이지와 관계가 있는 내용이여야 합니다.

{% highlight html %}
<article>
  <section>
      <h1>section 요소</h1>
      <p>내용물</p>
  </section>
  <footer>
      <address>
          <p>전다훈</p>
          <p>2022.08.04</p>
      </address>
  </footer>
  <!-- 콘텐츠 추천, 광고˚ -->
  <aside>
      <iframe src="ad.html"></iframe>
  </aside>
</article>
{% endhighlight %}
