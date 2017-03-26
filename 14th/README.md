# 14번째 시간 (복습)

## CSS3

> Cascading Style Sheet 3

CSS2가 분량이 많다보니 나눠서 3에서 구현했다.

- CSS Transform
- CSS Animation

## Prerequire

### 브라우저의 해석법

[영상 참고](https://www.youtube.com/watch?v=ZTnIxIA5KGw)

#### HTML

1. HTML 코드 읽어들임 (Parsing)
2. 토큰화 (Tokenizer)
3. DOM 객체 생성
4. DOM 트리 생성
5. Style Tree와 매칭
6. 요소를 배치 (Layout 단계 = Reflow)
7. 화면에 보여줌

#### CSS
1. CSS 코드 읽어들임
2. 토큰화 (Tokenizer)
3. Style Tree (DOM Tree와 비슷한 형태)


### 렌더링 엔진

1. webkit (Safari)
2. blink (Opera, Chrome)
3. trident (MS Edge, IE)
4. gecko (Firefox)

### 자원 (Resource)

해석할 때 (Parse, Tokenize, DOM Tree)는 CPU 그릴 때 GPU 사용

CPU는 연산왕
GPU는 그림왕

CPU가 해석하고 GPU에 보내서, GPU가 화면에 그림

> CPU를 거치는 과정을 줄일 수록 렌더링 속도는 빠름

[CSS Triggers](https://csstriggers.com/)

## CSS Transform

> 형태를 변경시키는 행위를 할 수 있다.

1. 이동 (Translate)
2. 크기 조절 (Scale)
3. 회전 (rotate)
4. 비틀기 (skew)

* 다른 요소에 영향을 주지 않는다.
* CPU가 관여하지 않는다. (GPU만 관여)


### Translate

```css
/*
 * 자기 자신을 기준으로 움직인다.
 * percentage 단위를 쓸 경우, 자기 자신이 보이는 지점을 기준.
 */
/* selector */ {
  transform: translate(x, y);
}
```

### Rotate

요소의 회전각도를 조절하는 속성

[테스트](https://www.google.co.kr/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=do+a+barrel+roll&*)

- rotate
- rotateX
- rotateY

```css
/*
 * 단위는 deg를 사용한다.
 */
/* selector */ {
  transform: rotate(값);
}
```

### Scale

요소의 크기를 변형하는 속성

```css
/*
 *
 */
/* selector */ {
  transform: scale(값);
}
```

### Skew

요소를 비스듬히 비트는 속성

[테스트](https://www.google.co.kr/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=askew&*)

```css
/*
 * 단위는 deg를 사용한다.
 */
/* selector */ {
  transform: skew(값);
}
```


## CSS Animation

1. 트리거 기반 애니메이션 (transition)
2. 그냥 애니메이션 (animation, @keyframes)

### Transition

- transition
- transition-duration (시간)
- transition-property (어떤 속성에)
  - top, color ...
- transition-timing-function (가속도를 어떻게 넣을 건 지)

[Bezier-Curv](cubic-bezier.com)

## Animation

내가 어느정도 제어 가능한 단계에서 애니메이션을 부여
트랜지션은 A에서 B까지의 변화를 지정, 애니메이션은 키프레임으로 그걸 지정

- animation-fill-mode: 애니메이션이 끝났을 때 어떻게 할 것인가를 결정
  - fowards ...
- animation-iteration-count: 애니메이션 반복 횟 수를 결정
  - 숫자, infinite
- animation-delay: 지연 시간을 결정

애니메이션 명세
최초: [ 박스 ]
최종: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [ 박스 ]
```css
.box {
  width: 150px;
  height:150px;
  background: crimson;

  /*
   * animation-duration
   * animation-(keyframe)name
   * animation-timing-function
   */
  animation: 0.3s move-box ease;
}

@keyframes move-box {
  0% {
    transform: translate(0, 0);
    background: red;
  }

  100% {
    transform: translate(100%, 0);
    background: gray;
  }
}

또는

@keyframes move-box {
  from {
    //
  }

  to {

  }
}
```


## Reference

[구글 과부화 테스트 - 저그러시](https://www.google.co.kr/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=zerg+rush&*)
[High Performance Animations](https://www.html5rocks.com/en/tutorials/speed/high-performance-animations/)
[2D transform's translate() vs absolute positioning: Performance](https://www.youtube.com/watch?v=NZelrwd_iRs)
[Myth busting the HTML5 performance of transform:translate vs. top/left](https://blog.tumult.com/2013/02/28/transform-translate-vs-top-left/)
[구글 웹디자이너](https://www.google.co.kr/webdesigner/thankyou/index.html)
[Double Click](https://www.doubleclickbygoogle.com/ko/solutions/digital-marketing/creative-solutions/)
