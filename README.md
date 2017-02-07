# fecamp_htmlcss_2nd
패스트캠퍼스 HTML&amp;CSS 입문 2기

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



|Attr|Value|Comment|
|---|---|---|
|name|viewport|모바일에서 접근 했을 때, 어떻게 보여줄 것인가를 정하는 속성|
|content|initial-scale|1:단말 사이즈에 맞게 사이즈가 조정 됨|
|content|width|device-width: 기기의 가로사이즈 (모바일에서만 사용하며, 거의 사용하지 않음) |

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




----

iphone 사이트 따라해보기


----

#### Reference

[Emoji](http://unicode.org/emoji/charts/full-emoji-list.html)
[Microdata](): 검색엔진 상위에 노출하기 위한...
