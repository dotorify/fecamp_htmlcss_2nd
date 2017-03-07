# fecamp_htmlcss_2nd
패스트캠퍼스 HTML&amp;CSS 입문 2기

----
## 목차
- [1. 수업 목표](#수업-목표)
- [2. 보충 수업 관련 \(복습\)](#보충-수업-관련-복습)


----

## 수업 관련

**목표**
- 이론적으로 HTML / CSS 접근
- 실무레벨에서 접근
- 미래의 기술에 대해 아는 것

**보충 수업 관련 (복습)**
- 2월 25일 오후 2시부터 4시 (3주차 토요일)
- 3월 11일 오후 2시부터 4시 (5주차 토요일)
- 3월 25일 오후 2시부터 4시 (7주차 토요일)


## 1st - 2017.02.07

**HTML을 작성할 때, 고민해야할 점**
- 이 HTML 요소가 정말 최선인가?
    - 최선이라고 생각했다면 그에 대한 근거를 있어야한다.
- 마크업에 정답은 없다.
- HTML에 본연적 의미를 변경하지 말아라.
- w3schools.com 들어가지 말 것. 잘못 된 내용이 많다.
    - [MDN - Mozila Developer N](https://developer.mozilla.org/ko/)이 잘되어 있다.

**CSS을 작성할 때, 고민해야하는 것**
- Design과 일치하는 CSS를 작성하도록 노력할 것

### 1. !DOCTYPE html
```HTML
<!DOCTYPE html>
<!--
  - DOCTYPE html
  - DOCTYPE = Document Type => 문서의 타입
   1) 이 문서가 HTML|XHTML|XML|SVG 인지 (즉, 어떤 언어인지)
   2) 이 문서가 HTML이라면 어떤 버전인지
  - 최신 버전의 HTML을 사용하겠다는 의미. `17.02기준 5.1을 사용하겠다)
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

##### 3.1.1. ViewPort

> 웹사이트에 접근해서 유저가 바라보는 뷰

<table>
  <thead>
    <th>Property</th>
    <th width="150px">Value</th>
    <th>Comment</th>
  </thead>
  <tbody>
    <tr>
      <td>name</td>
      <td>viewport</td>
      <td>모바일에서 접근 했을 때, 어떻게 보여줄 것인가를 정하는 속성</td>
    </tr>
    <tr>
      <td rowspan="5">content</td>
      <td>initial-scale</td>
      <td><span>기본 배율.</span><br><span>1:단말 사이즈에 맞게 사이즈가 조정 됨</span></td>
    </tr>
    <tr>
      <td>minimum-scale</td>
      <td>최소 축소 가능 배율 ( 0.1 ~ 1 사이 )</td>
    </tr>
    <tr>
      <td>maximum-scale</td>
      <td>최대 확대 가능 배율 (1 ~ 4 사이 )</td>
    </tr>
    <tr>
      <td>width</td>
      <td><span>가로 길이 (device-width, px 고정값)</span><br><small>device-width: 기기의 가로사이즈 (모바일에서만 사용하며, 거의 사용하지 않음)<small></td>
    </tr>
    <tr>
      <td>user-scaleable</td>
      <td><span>유저에게 확대/축소를 할 수 있게 할 것인지 ( true | false )</span><br><span>(권장하지 않음.)</span></td>
    </tr>

  </tbody>
</table>


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


##### 3.1.2. Charset (Character Set)
> 문자열 집합

<table>
  <thead>
    <th>Property</th>
    <th>Value</th>
    <th>Comment</th>
  </thead>
  <tbody>
    <tr>
      <td rowspan="4">charset</td>
      <td>UTF-8<br>(unicode 8bit)</td>
      <td>현대에서 사용하는 (이모티콘 포함)  전 세계 대부분의 문자열을 지원</td>
    </tr>
    <tr>
      <td>EUC-KR</td>
      <td>공식적으로 한글만 지원하지만 모던 브라우저들은 UTF-8로 자동 변환 해주기도 한다.</td>
    </tr>
    <tr>
      <td>UTF-16</td>
      <td>...</td>
    </tr>
    <tr>
      <td>UTF-32</td>
      <td>...</td>
    </tr>
  </tbody>
</table>

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


Example:
```html
<link rel="icon" href="favicon.png">
<!--
  - favicon 불러오는 방법
  - IE 구버전을 대응하지 않아도 되는 경우: png파일
  - IE 10이하를 대응해야 되는 경우: ico파일
-->
```

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

## 3rd - 2017.02.14

### HTML
> HTML: Hyper Text Markup Language
>  링크로 이동이 가능한 마크업 언어

```
- HT(Hyper Text)
  - 링크 (Anchor)
- ML(Markup Language)
```


#### History

```
1991년 HTML 1.0 (20개의 요소)
1993년 HTML 1.0 표준
...
1999년 HTML 4.01 표준
...
2003년   XHTML 1.0
2004년   XHTML 1.1
2007년   XHTML 2.0 (망함)
...
2014년 HTML 5 표준
2016년 HTML 5.1 표준

```


#### HTML5 API [W3C WebAPIs ](https://www.w3.org/TR/html5/webappapis.html), [참고](http://html5index.org/)

- Geolocation
- Local Storage
- Session Storage
- Service Worker
- Canvas (bitmap)

#### List

```html
<ul>
  <li></li>
</ul>

<ol>
  <li></li>
</ol>
```

* div밑이나 li요소 밑에 P가없으면 익명으로 P요소가 있다고 인식한다.

#### Nav

```html
<nav></nav>
```




## 4th - 2017.02.18

### CSS

> Cascading Style Sheet

- 폭포수가 흐르는 형태
- 부모요소의 CSS가 자식요소에 영향을 미친다.
- flow(흐름)
- 보통 요소가 쌓이는 형태 => Normal Flow

##### Style
- HTML/XML에 디자인을 씌우는 (표현을 입히는)

##### Sheet
- 명세서

##### Style 작성시 고려해야하는 사항
- 디자인으로 인해 HTML의 본연적 의미를 변경하지 마라.
- 리팩토링 할 수 있는 여지가 있다고 생각하면 안된다.
- 테스트 케이스, 예외상황, 모듈화
- FontSize는 수정이 용이하도록 작성해야한다.

##### 웹 폰트 고려해야하는 사항
- IE6 이상 지원
- 용량은 적당한가
- 한글을 사용할경우 [Spoqa](https://spoqa.github.io/spoqa-han-sans/ko-KR/)를 고려해 볼 것
- CSS내에서 @Import를 사용하는 방법보다 link에서 불러오는 방법이 빠르다.
- FOUC방지코드 \<link rel="stylesheet" href="font주소">
- e.g. \<link rel="stylesheet" href="//fonts.googleapis.com/earlyaccess/hanna.css">


----

#### Fonts

- Feature
  - 상속 === inherit === cascading
  - 하위 요소 전체가 폰트를 상속
  - input 요소 제외
  - button 요소 제외
  - textarea 요소 제외

- Property
  - Font
    - font-family: 폰트의 집합
    - font-size: 폰트의 크기
    - line-height: 폰트의 행간
    - letter-spacing: 폰트의 자간
    - font-weight: 폰트의 굵기
  - Text
    - text-align: 정렬
    - whitespace: 공백문자를 어떻게 처리 할지
    - text-transform: 문자 변형, 대소문자
    - text-overflow: 문자가 넘칠 경우
    - line-clamp: 문자가 넘칠경우, 여러줄, 지원율 낮음


- font-size
  - pixel (px)
    - 하나의 그래픽을 이루는 가장 작은 단위
    - default font size: 16px;
    - 맥, iOS의 기본 폰트는 APPLE SD Gothic NEO
    - 디자인에서 20px => 10px (레티나)
    - 맥, iOS에서는 11px로 설정해야 디자인 시안과 동일하게 나온다.
  - em
  - rem (root em)
    - HTML 폰트 사이즈를 기준으로 계산
    - 브라우저 지원율이 낮음 (IE11부터 지원)
  - pt (point)
    - 잘 사용하지 않음
    -
  - %
    - 부모 요소를 기준으로 %값을 계산
    - 100% = 부모요소의 폰트사이즈 = 16px
    - 125% = 1.125 -- 16px을 기준으로 18px로 만드는 방법

##### line-height

- 폰트사이즈별/브라우저별 고려해주어야한다.
- TODO

##### font-family

```css
/* selector */ {
  font-family: <family-name> <generic-name>;
}
```

- <family-name>
  - case insenstive

- <generic-name>
  - serif: 명조, 획이 있는 글꼴
  - sans-serif: 고딕, 획이 없는 글꼴


For Example:
```css
/**/ {
  font-family: "APPLE SD Gothic NEO", sans-serif;
  /*
   * APPLE SD Gothic NEO 폰트가 있다면 사용해서 보여줌
   * 아니라면 기본 고딕 폰트
   * 리눅스/윈도우에서 봤을 때는 APPLE 폰트가 없기 떄문에 기본 고딕 폰트
   */
}
```


  <table style="display:none;">
    <thead>
      <th colspan="2"></th>
      <th>폰트</th>
    </thead>
    <tbody>
      <tr>
        <td colspan="2">맥, iOS</td>
        <td>APPLE SD Gothic NEO</td>
      </tr>
      <tr>
        <td>안드로이드</td>
        <td>Reference</td>
        <td></td>
      </tr>
    </tbody>
  </table>

##### letter-spacing

Usage:
```css
/* selector */ {
  letter-spacing: ;
}
```

- 음수 가능 (-값 가능)
- 서브픽셀(소수점) 가능 (IE제외)


##### font-weight

Usage:
```css
/* selector */ {
  font-weight: <size>;
}
```

- size
  - 100~900 사이의 값
  - 100: Thin (Hairline)
  - 200: Extra Light (Ultra Light)
  - 300: Light
  - 400: Normal
  - 500: Medium
  - 600: Semi Bold (Demi Bold)
  - 700: Bold
  - 800: Extra Bold (Ultra Bold)
  - 900: Black (Heavy)

> 폰트별 지원하지않는 font-weight size가 존재한다.
> 이 경우, 가장 가까운 숫자ㄹ에 맞게 size를 변경한다.
> 100 ~ 500 = 400으로 변경
> 600 ~ 900 = 700으로 변경



##### text-align

Usage:
```css
/* selector */ {
  text-align: <size>;
  /*
   * <size>
   *   center;
   *   left;
   *   right;
   */
}
```

```css
/* 말 줄임을 하는 방법 Trick! */
body {
  white-space:nowrap;
  overflow:hidden;
  text-overflow: ellipsis;
}
```

한국어는 justify-content를 지원되지 않는다. 지원율이 현저히 낮다.


### Box Model

[자세한 내용](http://brunch.co.kr/@techhtml/21)

#### Display

- normal flow
- 모든 요소는 기본적으로 쌓이는 구조 (위에서 아래로, 좌에서 우로)

- block vs inline

- block
  - 블록 서식 문맥(block formatting context)
  - 한줄을 다 차지함
  - width,height를 설정하더라도 (자신이 가질 수 있는) 한 줄을 다 가짐
  - 박스의 너비 = width + (padding-left, padding-right) + (border-left, border-right)
  - 박스의 높이 = height + (padding-top, padding-bottom) + (border-top, border-bottom)

  - margin은 너비,높이계산에 포함되지 않음
- inline
  - 인라인 서식 문맥(inline formatting context)
  - 보여지는 것과 실제 크기가 다르다
  - width 사용 불가
  - 크기 계산 로직
    - 비주얼 크기
      - TOOD
    - 실제 크기
      - 너비: 콘텐츠 크기 + (padding-left, padding-right) + (border-left, border-right)
      - 높이: line-height
- inline-block
  - 한줄을 다 차지하지 않음
  - 텍스트와 동일하게 취급 하는데
  - block처럼 width, height, padding 등을 계산 한다.
  - inline에서 보여지는 것과 실제크기가 다를 때 실제크기에 맞출 수 있다.


```css
p {
  padding: 0 20px;
  width: 100%;
  box-sizing: border-box;
  /*  width 와 height 속성이 padding 및 border를 포함하며, margin을 포함하지 않는다. */
}
```


#### Float

> Float는 이미지를 왼쪽/오른쪽으로

- Float된 요소의 높이는 부모가 알지못한다.





## 5th - 2017.02.21

브런치 사이트 만들어보기

## 6th - 2017.02.25

<img src="https://cloud.githubusercontent.com/assets/5626399/23326438/efa592e0-fb40-11e6-899d-f638cbd57073.png" alt="Brunch 1st List">

- 리스트(UL, LI)로 작성


## 보충수업 - 2017.02.25

#### div

> division

- 그룹을 이루기위한 요소

## 7th - 2017.02.28

## 8th - 2017.03.04

```html
  (3) 하드웨어 (센서)
    - 세로모드(portrait): 세워놓은 상태
    - 가로모드(landscape): 엎어놓은 상태
    - Geolocation API, 위치정보 (네트워크 위치를 기점, HTTPS)
    - [HTTPS](https://ko.wikipedia.org/wiki/HTTPS)
    - 진동: Vibration API
    - 사진: Camera API

```

### Form

```html
<form action="{처리하는 코드}" method="{Request Method}">
  <!--
    - Action: 처리하는 코드
    - Method: 요청 메소드
      - Get, Post
  -->
</form>
```

#### input

1. Feature

- inline 요소
- 기본적으로 font를 상속받지 않는다. (font: inherit)
- label 태그와 같이 사용한다. (접근성 측면에서 장점이 있다.)

2. Attribute

2.1. Type
<table>
  <thead>
    <th>속성</th>
    <th>모바일</th>
    <th>비고</th>
  </thead>
  <tbody>
    <tr>
      <td>text</td>
      <td>기본 키보드</td>
      <td>생략 가능</td>
    </tr>
    <tr>
      <td>radio</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>tel</td>
      <td>전화번호 키보드</td>
      <td></td>
    </tr>
    <tr>
      <td>number</td>
      <td>숫자 키보드</td>
      <td></td>
    </tr>
    <tr>
      <td>email</td>
      <td></td>
      <td></td>
    </tr>
    <tr>
      <td>url</td>
      <td>.com등의 URL 입력을 지원하는 키보드</td>
      <td></td>
    </tr>
    <tr>
      <td>date</td>
      <td>날짜를 선택할 수 있는 콤보박스</td>
      <td>기본값: 오늘</td>
    </tr>
    <tr>
      <td>time</td>
      <td>시간을 선택할 수 있는 콤보박스</td>
      <td>기본값: 현재 시간</td>
    </tr>
    <tr>
      <td>datetime-local</td>
      <td>날짜와 시간을 선택할 수 있는 콤보박스</td>
      <td>날짜와 시간을 모두 선택할 수 있다.</td>
    </tr>
    <tr>
      <td>password</td>
      <td></td>
      <td>password character로 표시된다.</td>
    </tr>
    <tr>
      <td>submit</td>
      <td></td>
      <td></td>
    </tr>
  </tbody>
</table>

Tip. iOS에서 input shadow 지우는 방법
Usage:
```css
/* selector */ {
  -webkit-apperance: none;
}
```

2.2. Placeholder

Usage:
```html
<input type="text" placeholder="{인풋 내에 보여질 텍스트}">
```

2.3. Required

- 필수 여부 적용이 가능하다.
- Safari에서는 지원하지 않는다.

Usage:
```html
<input type="text" required>
```

2.4. Pattern

- 넣을 수 있는 패턴을 정할 수 있다.
- Safari에서는 지원하지 않는다. Android에서는 가능
- [Regex101 참고](https://regex101.com/)

Usage:

```html
<input type="text" pattern="{Regular Expression}">
```

2.5. Min/Max

- type이 number일 경우에만 가능
- validation 가능
- Safari에서는 지원하지 않는다. Android에서는 가능

Usage:

```html
<input type="text" min={최소값} max={최대값}>
```

2.6. minlength/maxlength

- type이 number일 경우에만 가능
- validation 가능
- Safari에서는 지원하지 않는다. Android에서는 가능

Usage:

```html
<input type="text" minlength={최소길이} maxlength={최대길이}>
```


### 반응형 웹 디자인

> RWD: Responsive Web Design

As-is: PC면 PC, Mobile이면 Mobile 별도 대응
To-be: PC로 보던, 모바일로 보던 그 기기에 최적화된 UI를 제공


> 해상도대응 - 미디어 쿼리
> 이미지대응 - 이미지 변경
> 그리드대응 - 레이아웃 변경


Usage:
```css
@media <TYPE> and (CONDITION) {
  /* Rules */
}
```

Example:
```css
/* 브라우저의 가로사이즈가 720px넘는 경우, 폰트사이즈를 14px */
@media screen and (min-width:720px) {
  body {
    font-size: 14px;
  }
}
```

개발 방법
1. Mobile First
2. Desktop First

주의할 점
- 미디어 쿼리는 기본 CSS 아래에 위치 할 것.
- [모바일] Margin값 부여하는 것은 지양할 것.
- Percentage Unit 지향


## 9th - 2017.03.07

> Step1~3 진행 간 실제 데이터를 사용하지 않고 더미 데이터로 작업한다.

### 개발 프로세스

#### Step1. 기획
- 기획
- 상위기획
    - UI Components 정의
- 상세기획
    - 디자이너와 같이 UI 개발
    - QA
    - BE 개발

#### Step2. UI 디자인
- 인터렉션 디자인

#### Step3. UI 개발
- HTML, CSS

#### Step4. Back-end 개발
- 서버 개발 (e.g. Domain, DB, API AJAX ...)

#### Step5. QA

#### Step6. 배포

---

<figure>
  <img src="http://www.logicalposition.com/couch/uploads/image/blog-articles/how-the-web-works/http.png" alt="">
  <figcaption>[Figure 1] HTTP Request & Response</figcaption>
</figure>

<figure>
  <img src="https://i-msdn.sec.s-msft.com/dynimg/IC564167.png" alt="">
  <figcaption>[Figure 2] MVVM Pattern</figcaption>
</figure>

---

신입 때 들었던 생각
> 아래 나열된 순서대로 생각을 해보면 좋다.

- 생각보다 어렵다.
- 어떤 요소를 사용해야하지?
    - 당장은 크게 고민하지 말아라.
- 클래스명은 어떻게 지을까?
  ```css
  /*
   * Tip. Component이름 + 요소의 목적
   *
   * example:
   * .list
   * .list .list-thumb
   * .list .list-big (폰트크기가 큰)
   */
  ```
  or
  - [Darum Naming Convention](http://darum.daum.net/convention/name)
  - [Naver Naming Convention](http://nuli.navercorp.com/sharing/fe/coding)
  - [Airbnb Naming Convetion](https://github.com/airbnb/css)

- 디바이스
  ```
  ├── 하드웨어
  │   ├── PC (마우스)
  │   └── 모바일 (터치)
  │
  └── OS (default browser)
      ├── iOS: Safari
      ├── Android: Chrome
      ├── Window: IE Edge
      ├── Mac: Safari
      └── Linux: Firefox

  ==========================
  모바일과 PC를 나누는 기준점
  1. Wild / Tilt (?)
  2. 터치 / 커서
  ```
- 브라우저 지원은 어디까지 고려해야할까?
  ```
  - 정책을 세울 때 정해야 한다.
  - IE버전을 몇 까지 지원할지 고민해야 한다.
    > choeun's: 최신버전 -2 단계까지 지원 (IE 9~10부터 지원)
  - 서로다른 브라우저에서 최대한 동일하게 보이도록 하려면
    > Reset.css 또는 Normalize.css를 사용하면 좋다.
      (모든 브라우저에서 똑같이 보이도록 하는 것은 힘들다.)
  ```
- 예외처리 (정책)
  ```
  - 콘텐츠 길이가 길어질 경우
    > 말 줄임처리
  - 부모 사이즈가 변경되는 경우
    > 부모 요소가 변경됨에 따라 자식 요소의 사이즈도 같이 변경 되도록 하는 것이 좋다.
      부모 width값 설정, 자식에는 width값 최대한 설정하지 않는다.
  - 기기가 달라질 경우
  - 모바일페이지를 개발해놓고 PC에서 접속했을 경우
  ```
- 접근성
  ```
  우리나라: 장애인 차별 금지 및 권리 규제에 관한 법률(장차법) => KWCAG 2.1
  국제: WCAG

  핵심: 누구나 사용가능할 수 있어야한다.

  예를 들어,
  Contrast Ratio 비율 준수해야한다.
  폰트컬러가 #666보다 미만이면 장차법 위반이다.
  ```
- 자바스크립트
- 범용성
- 디버깅
  ```
  - 크롬 최신버전, Mac OS, 내 사이트의 사이즈와 브라우저 사이즈를 비교했을 떄, 어떤 상황에서 장애가 나는가
  - 내 사이트가 width가 900px, 브라우저 크기가 그 보다 작아요. 근데 xx가 안되요. 왜 안될까?
  ```

어떻게 좋은 개발자가 될 수 있을까?
- 오픈소스 기여

요즘 개발자들은 어느정도 공부하나요?
- HTML, CSS, Javascript(ECMA-2015)
- Test (Mocha, Jest) ,Test Case 작성법
- Front-end Framework and libraries (Angular, React, Vue)
- Front-end 개발 방법론 (MVVM 채턴 , MV* 패턴)
- 빌드환경에 대한 이해(Webpack)
- 프로그래밍 언어의 기원 (객체지향과 함수형의 차이)
- 객체지향이 뭔지, 함수형이 뭔지, 절차지향이 뭔지
- 컴파일러에 대한 이해, OS에 대한 이해, 브라우저에 대한 이해

신입 프론트엔드 개발자가 알아야할 것 들
- 버전관리 (git, svn)
- 오픈소스 기여해본 경험
- 블로그 운영
- HTML, CSS, 웹표준, 웹접근성, 시맨틱웹
- 자바스크립트의 기초


### 학습에 도움이 되는 사이트

- [Mozilla MDN](https://developer.mozilla.org/ko/)
- [IE CSS 호환성](https://msdn.microsoft.com/en-us/library/hh781508(v=vs.85).aspx)
- [KWCAG 2.1 한국형 웹 콘텐츠 접근성 지침](http://www.wah.or.kr/Participation/guide.asp)
- [WCAG 2.0 지침이 전하는 전경색과 배경색의 명도 대비](http://naradesign.net/wp/2009/07/01/947/)
- [WCAG 2.0 Documentation](https://www.w3.org/WAI/intro/wcag)
- [프론트엔드에 테스트를 도입](http://techhtml.github.io/blog/2016/05/)

> W3School 들어가지 말 것 (표준에 위배되는 내용들이 포함되어 있음.)

### Glossary

- Crawling: 로봇 혹은 사용자가 사이트를 긁어가는 행위
- HasLayout: IE만의 Layout


## 수행한 과제

- [네이버 모바일 회원가입 페이지](http://codepen.io/dotorify/pen/KWMRJw)
- [네이버 모바일 메인 페이지](http://codepen.io/dotorify/pen/EWNYgW)

## Reference

- [Emoji](http://unicode.org/emoji/charts/full-emoji-list.html)
- [Microdata](): 검색엔진 상위에 노출하기 위한...
- [SK 신현석:HTML5.1 변경사항](https://hyeonseok.com/soojung/webstandards/2017/01/28/808.html)
- [CSS 반복 체크:CSS-Purge](https://github.com/rbtech/css-purge)
- [만들어볼만한 페이지:더가디언](https://www.theguardian.com/international)
- [W3C 한국어 텍스트 레이아웃 및 타이포그래피를 위한 요구사항](https://www.w3.org/TR/2013/WD-klreq-20130514/korean/)
- [Google Fonts - Early Access](https://fonts.google.com/earlyaccess)
- [W3C HTML Validator](https://validator.w3.org/)
