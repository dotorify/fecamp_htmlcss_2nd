# fecamp_htmlcss_2nd
패스트캠퍼스 HTML&amp;CSS 입문 2기

----
# 목차

#### [1. 수업 목표](#수업-목표)
----

## 수업 목표
- 이론적으로 HTML / CSS 접근
- 실무레벨에서 접근
- 미래의 기술에 대해 아는 것

## 보충 수업 관련 (복습)
- 2월 25일 오후 2시부터 4시 (3주차 토요일)
- 3월 11일 오후 2시부터 4시 (5주차 토요일)
- 3월 25일 오후 2시부터 4시 (7주차 토요일)

## 1st - 2017.02.07

<b>HTML을 작성할 때, 고민해야하는 것</b>
- "이 HTML 요소가 정말 최선인가?"
- 최선이라고 생각했다면 그에 대한 근거를 있어야한다.
- 마크업에 정답은 없다
- w3schools.com 들어가지 말 것. 잘못 된 내용이 많다. => [MDN](https://developer.mozilla.org/ko/)이 잘되어 있다.

<b>CSS을 작성할 때, 고민해야하는 것</b>
- Design과 일치하는 CSS를 작성하도록 노력할 것

### 1. !DOCTYPE html
```HTML
<!DOCTYPE html>
<!--
  - DOCTYPE : HTML 버전 (최신 버전을 사용하겠다는 의미. "17.02기준 5.1을 사용하겠다")
  - 모드 종류
    * quirks mode(default) : 오래된 웹사이트가 현재의 브라우저에도 이전 처럼 잘 보여야 한다.
-->

<!-- head, body의 부모 요소 -->
<html>
  <!--
    - html의 (자식) 요소
    - html 문서의 최고 조상 요소 (루트 요소)
      * html 하위에는 head와 body요소가 반드시 존재해야 한다.
  -->
  <head></head>
  <body></body>
</html>

```

### 2. [lang=""]

```html
<!DOCTYPE html>
<html lang="ko">
<!--
  "이 웹사이트는 한글 문서입니다. (웹접근성 차원에서 스크린리더에서 사용)"
-->
</html>
```

### 3. Head

```html
<!DOCTYPE html>
<html>
  <head>
    <!--
       - 두뇌
       - 로봇에게 전달해야하는 정보를 가지고 있음
       - (1) 웹 브라우저
         * IE, Chrome, Safari, Opera, Firefox
       - (2) 검색엔진
         * 구글
       - (3) 스크린리더, AT(Assistant Tool - 보조 도구)
         * "한국어를 한글로 읽어주는 ..."
       - (4) 크롤러
         * 페이스북과 같이 페이지 내 데이터를 긁어가는...
    -->
  </head>
</html>
```

#### 3.1. Meta

- 닫는 태그
    - 텍스트/컨텐츠를 포함하는 요소
    - title, ...
- 빈 태그 (Void Elements/Singleton Tags)
    - 닫는 태그가 없는 요소 (9~10가지)
    - meta, ... [기타 종류는 여기서 확인](http://webdesign.about.com/od/htmltags/qt/html-void-elements.htm)


<table>
  <thead>
    <th>속성</th>
    <th>값</th>
    <th>설명</th>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>viewport</td>
      <td>모바일에서 접근 했을 때, 어떻게 보여줄 것인가를 정하는 속성</td>
    </tr>
    <tr>
      <td>content</td>
      <td>initial-scale</td>
      <td>1:단말 사이즈에 맞게 사이즈가 조정 됨</td>
    </tr>
    <tr>
      <td>content</td>
      <td>width</td>
      <td>device-width: 기기의 가로사이즈 (모바일에서만 사용하며, 거의 사용하지 않음)</td>
    </tr>
  </tbody>
</table>

- viewport에서 사용할 수 있는 content
    - initial-scale: 최대 확대값
    - width: 가로 길이
    - maximum-scale: 최대 확대값 (1~4)
    - minimum-scale: 최대 축소값 (0.1 ~ 1 사이)
    - user-scaleable: (true|false) 유저가 확대 축소 기능을 사용할 수 있게 할 지 (권장 x)

````
# 실무 TIP - for iPhone safari
" initial-scale, maximum-scale, minimum-scale을 같은 값을 넣으면 확대, 축소가 되지 않음. " - 웹 접근성이 떨어지는 단점이 있음,
````

Example:
````html
<!DOCTYPE html>
<html>
  <head>
    <meta name="viewport" content="initial-scale=1">
  </head>
</html>
````



charset: 문자열 집합

|Attr|Value|Comment|
|---|---|---|
|charset|UTF-8<br>(unicode 8bit)|현대에서 사용하는 (이모티콘 포함)  전 세계 대부분의 문자열을 지원|
||EUC-KR|공식적으로 한글만 지원하지만 모던 브라우저들은 UTF-8로 자동 변환 해주기도 한다.|

Example:
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
  </head>
</html>
```

#### 3.2. Title

- 페이지의 제목을 설정하는 요소

Example:
````html
<!DOCTYPE html>
<html>
  <head>
    <title>패스트캠퍼스 HTML CSS 입문 2기</title>
  </head>
</html>
````


----

Sample

````html
<!-- template.html -->
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>홈페이지 제목</title>
    <meta name="viewport" content="initial-scale:1,width:device-width"
  </head>
  <body></body>
</html>
````

----

### 4. Body

````html
<!DOCTYPE html>
<html>
  <head>
  </head>
  <body>
      <!--
        [ Header ]
        [ Contents ]
        [ Footer ]

        ....

        [ Contents | Header | Footer]
        - 만약 IE7을 대응해야 한다면?
          ==> 다음과 같이 사용 할 수도 있다. (방어코드 사용)
              <div class="header"></div>
              <div class="footer"></div>
              <div class="main"></div>
              <div class="section"></div>
              <div class="article"></div>

        - 최근 IE 몇 버전을 기준으로 대응 하는가?
          ==> IE10


        [ Contents - Semantic Tags ]
          - <main></main>
            * 이 페이지의 main 컨텐츠
            * 한 페이지에서 한 번만 사용 할 수 있다.
            * Android 4.* 에서는 지원하지 않음. http://caniuse.com/#search=main
            * e.g. 스크린리더에서 'main으로 바로가기'를 사용하면 이 영역으로 오게 되어있다.

          - <section></section>
            * 관심사 그룹에 따라 구획을 구분하기 위해 사용하는 요소
            * '반드시' 제목 요소(h1 ~ h6)를 가져야 한다.
              ==> Why? 이 섹션의 관심사가 무엇인지 로봇에 알려주기 위함.
            * e.g. Facebook의 Timeline Message 내 댓글, 컨텐츠 영역

          - <article></article>
            * 관심사 그룹에 따라 글을 작성하기 위해 사용하는 요소
            * '반드시' 제목 요소(h1 ~ h6)를 가져야 한다.
              ==> Why? 이 섹션의 관심사가 무엇인지 로봇에 알려주기 위함.
            * e.g. Facebook의 Timeline Message 1개

          ! section vs article
            * 독립적으로 존재해도 되는 경우 ==> article 사용
            * 용법은 거의 비슷하지만 독립적이냐의 여부에 따라 구분해서 사용

        [ Contents - Non Semantic Tags ]
          - <div></div>
            * 그룹을 짓기위해 있는 요소
            * 레이아웃을 짜기 위해서 or 방어 코드를 만들기 위해서
            ! 5번 중첩 된다면?
              ==> 두려워하지는 말되, 다시한번 살펴 볼 필요가 있다.

      -->

      <header>
        <h1>패스트캠퍼스</h1>
        <!--
          h1 요소는 한번 쓰는 것을 권장함.
        -->
        <h2>HTML CSS 캠프</h2>
        <!--
          h2 요소는 h1의 하위 제목

          h$과 h$ 사이에는 연관성이 있어야 한다.
        -->


        <!--
          명시적으로 구분하지 않은 예
            <h3>입문 강의</h3>
            <h4>1주차</h4>

            <h3>정복 강의</h3>
            <h4>1주차</h4>

          or

          명시적으로 구분한 예
            <section>
              <h3>입문 강의</h3>
              <section>
                <h4>1주차</h4>
              </section>
            </section>

            <section>
              <h3>정복 강의</h3>
              <section>
                <h4>1주차</h4>
              </section>
            </section>
        -->


      </header>
  </body>
</html>
````

## 2nd - 2017.02.11

> http: hypertext transfer protocol
> https: hypertext transfer protocol over SSL(Secure Socket Layer)

HTML을 잘 작성해야하는 이유
- 로봇(기계)가 조금 더 수월하게 읽어들이기 위함.

### 1. Anchor

```html
<a href=""></a>
```

- 필수 속성: href

### 2. Paragraph

```html
<p></p>
```

- 문장 요소

### 3. link

```html
  <link href="" rel="">
```

- 필수 속성: rel, href
- rel
  - relation
  - link해오는 리소스 파일의 포맷
- href
  - hyper reference
  - link해오는 리소스 파일의 경로

### 4. CSS

> CSS: Cascading Style Sheet

#### 4.1. 상속(Cascading, Inheritence)

- 부모 요소에 들어있는 CSS가 자식 요소에 영향을 준다. (A.K.A. cascading 하는 구조)
- cascading => 폭포가 흐르는 형태

#### 4.2. Selector

- Tag Selector

```css
html {
  /* Root 요소 */
}

body {
  /* 일반적으로 body에서부터 CSS작성 시작 */
}
```

- Class Selector (.)

```css
.theme-dark {/** */}

.theme-light {/** */}
```

- Descendant Combinator (&nbsp;&nbsp;)

```css
.menu h2 {/** */}
```


#### 4.3. Box Model

- 모든 HTML 박스(=요소)는 사각형(box)으로 이루어져 있다.

<table>
  <thead>
      <th>속성</th>
      <th>설명</th>
  </thead>
  <tbody>
    <tr>
      <td>width</td>
      <td>가로 길이, 너비</td>
    </tr>
    <tr>
      <td>height</td>
      <td>세로 길이, 높이</td>
    </tr>
    <tr>
      <td>padding</td>
      <td>
        <p>박스의 외곽선에서부터 내부 컨텐츠 사이의 여백</p>
        <p>top, right, bottom, left / 시계방향</p>
        <p>padding-top, padding-bottom / 각 방향에만</p>
        <p>border (외곽선)</p><p>  - 포맷: {width} {style} {color}</p>
        <p> - e.g. 1px solid #000000; === 1px solid #000;</p>
        <p>엔진이 읽는 방법: 순차적으로 읽다가 4개가 아니면 처음부터 다시 읽는다.</p>
      </td>
    </tr>
    <tr>
      <td>margin</td>
      <td>
        <p>박스와 박스 사이의 여백</p>
        <p>배경색을 넣을 수 없다.</p>
        <p>투명한 배경(transparent)</p>
        <p>중첩이 된다.(collapsping margin - margin 병합현상)  <a href="https://jsfiddle.net/8qcy5kuf/">jsfiddle 예제</a> </p>
      </td>
    </tr>
  </tbody>
</table>

#### 4.4. Overflow



### 5. Layout

1. 전통적인 Layout 구현법 (float)
    - IE에서 사용 (Flex를 지원하지 않아서)
2. 현대적인 Layout 구현법 (flex, grid)

```css

header {
  display: flex;
  /*
   * flex layout 구현을 위한 포석
   * 부모 요소에 display 속성을 이용하여 레이아웃을 정의
   */

  justify-content: center;
  /*
   * justify-content
   * - flex layout의 속성 중 하나
   * - 컨텐츠를 중앙으로 정렬 할 수 있다.
   * - text-align:center는 사용하면 안된다. Why? flex 범주이기 때문에
   *
   * 주의: 개발도구에서 모바일페이지 선택 후 단말에서 볼 때, 왼쪽 컨텐츠가 보이지 않는 경우가 있다. justify-content를 center로 설정했기때문인데 후에 media query에서 관련 내용을 다시 설명 예정.
  */
}

h1 {
  flex: 1
  /*
   *
   */
}

```


----

### 실습1. iPhone 페이지 만들기

- 시각적인 요소는 CSS로 제어가능하므로 속지마라.
- 반복되는 스타일이 있다면 재활용 해라. 일괄 리팩토링이 쉬워진다. (e.g. 클래스 생성)

1. 텍스트 중앙정렬
2. 폰트크기 조정


### 실습2. AMP 페이지 만들기


### 실습3. Google Web 

----

#### Reference

[Emoji](http://unicode.org/emoji/charts/full-emoji-list.html)
[Microdata](): 검색엔진 상위에 노출하기 위한...
