# 15번째 시간

일시: 2017년 3월 28일 화요일 19:30 ~ 22:30

주제: 웹 접근성을 학습하고, 지금까지 했던 내용을 복습한다.

## 웹 접근성

[Korean Web Content Accessibility Guidelines 2.1](http://www.wah.or.kr/Participation/%ED%95%9C%EA%B5%AD%ED%98%95%EC%9B%B9%EC%BD%98%ED%85%90%EC%B8%A0%EC%A0%91%EA%B7%BC%EC%84%B1%EC%A7%80%EC%B9%A82.1.pdf)

`한국형 웹 콘텐츠 접근성 지침`을 준수하지 않았을 경우, `장애인차별금지법`에 위반된다.

`한국형 웹 콘텐츠 접근성 지침`은 `WCAG 2.0`문서를 기준으로 한국 실정에 맞게 제작되었다.

해외의 `장애인차별금지법`: Web Accessibility - Section 508

### 준수 의무
- 기본적 측면


### 원칙

검사 항목이 체크해야할 하나 하나의 항목이라고 보면 된다.

- 인식의 용이성
- 운용의 용이성
- 이해의 용이성
- 권고성


#### 인식의 용이성

##### 대체 텍스트

텍스트 아닌 콘텐츠 = 이미지, 동영상, 오디오
```html
<img src="이미지 경로" alt="Alternative Text(대체 텍스트)">

<!-- 배경 이미지를 위한 설명 텍스트 -->
<div class="bg">

</div>
<span class="blind"></span>

<style>
  /* 배경 이미지 */
  .bg {
    /* IR (Image Replacement) 기법 */
    text-indent: -9999px; /* 텍스트만 날리는 방법 */
    /*
      - text-indent는 들여쓰기를 하는 것이므로 텍스트 크기만큼의 영역이 잡히는 단점이 있다.
    */
  }
  .blind {
    /* 요소 전체를 날리는 방법 (이 방식이 더 좋은 방법이다.) */
    position: absolute;
    left: -9999px;
  }
</style>

<!-- ////////////////////////////////////////// -->

<!-- 긴 설명문을 달아야 하는 경우 -->

<!-- 무조건 alt에 넣는 방법은 좋지않다. 이 경우 longdesc 속성을 사용하는 것이 좋다. -->
<img src="경로" longdesc="desc.html">

<!-- desc.html -->
<body>
  <h1>전국민 드립 배틀 ...</h1>
  <dl>
    <dt>응모자격</dt>
    <dd>넘치는 드립력과 새벽 3시 ....</dd>
  </dl>
</body>



<!-- ////////////////////////////////////////// -->

<!-- 긴 설명문을 달아야 하는 배경이미지 -->
<div class="bg">
  <h1 class="blind">...</h1>
  <dl class="blind">
    <dt>...</dt>
    <dd>...</dd>
  </dl>
</div>
```

##### 멀티미디어 대체 수단

- 자막, 수화, 대본이 제공되어야 한다.

##### 명료성


- 전경색(폰트색상, 콘텐츠색상)과 배경색이 4.5:1을 준수해야 한다.
- 만약 폰트사이즈가 14px 이상에 bold인 경우, 혹은 18px 이상인 경우는 3:1도 가능
- 확대가 가능한 경우 3:1
- 콘텐츠 사이에 구분이 가능해야한다. (구분선, 배경색을 달리)

```
- 콘텐츠는 색에 관계없이 인식될 수 있어야 한다.
- 고대비 모드를 하면 회색이 보이지 않는다.
```

#### 운용의 용이성

(6.2.2) 정지기능 제공은 네이버 쇼핑이동 정지/스킵 버튼 페이지 참고

(6.3) 광과민성 발작 예방

- 포켓몬 쇼크 영상과 같은 컨텐츠 안쓰는게 좋다.

(6.4) 쉬운네비게이션

- 네이버의 스킵네비게이션

```html
<!-- #main 선택시 id가 main인 곳으로 이동한다. -->
<a href="#main" class="skip-nav">메인 메뉴로 바로가기</a>

<div id="main">

</div>

<style>
  .skip-nav {
    visibility: hidden;
  }
  .skip-nav:focus {
    visibility: visible;
  }

  또는

  .skip-nav {
    position: absolute;
    top: 0;
    left: -9999px;
  }
  .skip-nav:focus {
    left: 0;
  }
</style>
```


## 지금까지 배웠던 내용 복습

### Font

- font-family (폰트의 집합)
- font-size (폰트의 크기)
- line-height (행간)
- font-weight (폰트의 굵기)
- letter-spacing (자간)
- color (색상)

### Text
- text-align (정렬)
- text-indent (들여쓰기)
- text-decoration (밑줄, 밑줄 제거)

### Box-model (박스가 어떻게 생겼는지)

> 레이아웃과 관련된 중요한 요소

- width
- height
- padding
- border
- margin
- box-sizing

### Layout

- float
- display model (block, inline)
- flex

### Flex box (부모)

부모요소에 `display: flex` 값을 부여하는 것으로 시작

- display: flex
- justify-content
- align-items
- flex-wrap: 요소가 늘어날 때 어떻게 처리할 것인지

### Flex box (자식)

- flex
- min-width

### Position

- position
  - static (기본값)
  - absolute
  - relative
  - fixed
- left, top, right, bottom
- z-index: 숫자가 높을 수록 z축이 위로


### Animation

- animation 속성: 시점 제어가 가능한
- transition 속성: 시점 제어가 불가능한
- transform 속성
  - translate
  - 크기 (scale)
  - 회전 (rotate)
  - 꺽기 (skew)

### Units
- px (pixel)
- %: 부모 요소에 상대적으로 변하는 값
  - padding-top: 100% (부모요소의 width)
  - width: 100% (부모요소의 width)
  - font-size: 100% (부모요소의 폰트 크기)
  - line-height: 100% (부모요소의 폰트 크기)
- em (자기 자신의 폰트 사이즈에 비례해서 변함)
  - 계산이 어렵다.
  - font-sise: 14px이라면 padding: 1em === 14px
- rem (root em; `<HTML>`요소의 폰트사이즈에 비례해서 변함)
- vw, vh (viewport width, viewport height)
  - 뷰포트는 기준으로 변하는 값
  - 브라우저 지원율이 낮음
  - 100vw = 뷰포트의 가로 사이즈
    - 아이폰 5s의 가로사이즈 = 320px = 100vw = 320px
  - 100vh = 뷰포트의 세로 사이즈
    - 아이폰 5s의 세로사이즈 = 480px = 100vw = 480px

### 고려해야할 것들

#### 공통
- 어느 버전까지 지원할 것인가
- 반응형 웹 디자인인가?

#### 데스크탑
- 디스플레이 사이즈 (화면 크기)
- 전체를 다 이용할 것인지? 부분만 이용할 것인지
  - 980px 고정하고 margin auto로 센터정렬 할 건지
  - 페이지 전체 다 쓸 건지

#### 모바일
- 화면 크기
- 센서 어느정도 쓸 건지
- 터치 영역 체크
  - 크기 어느정도 할 건지
