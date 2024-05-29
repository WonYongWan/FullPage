# FullPage
current ver1.0.0

## Language
[KOR](#KOR)<br/>
[JP](#JP)<br/>

# KOR
[제작 계기](#제작-계기)<br/>
[HTML 작성법](#HTML-작성법)<br/>
[CSS 관련 설명](#CSS-관련-설명)<br/>

## 제작 계기
기존에 널리 알려져 있는 fullpage 라이브러리를 상업적으로 사용하기 위해서는 비용을 지불해야 하는 부분이 있었는데 이를 무료로 사용하고자 하는 취지에서 제작하게 되었습니다.

## HTML 작성법
### introduce
#### fp_page_wrap는 필수. 나머지는 선택
```html
<!-- header -->
<!-- data-fpnum 속성 & 값 지정 후 해당 버튼 클릭시 지정 된 값과 같은 페이지로 스크롤 이동. 0 부터 시작 -->
<ul class="fp_menu_wrap">
  <li class="fp_menu" data-fpnum="2"></li>
  <li class="fp_menu" data-fpnum="2"></li>
  <li class="fp_menu" data-fpnum="3"></li>
  <li class="fp_menu" data-fpnum="4"></li>
</ul>

<!-- fullpage -->
<div class="fp_page_wrap">
  <div class="fp_page"></div>
  <div class="fp_page"></div>
  <div class="fp_page"></div>
  <div class="fp_page"></div>
  <div class="fp_page"></div>
</div>

<!-- navigation -->
<div class="fp_nav_wrap">
  <div class="fp_nav"></div>
  <div class="fp_nav"></div>
  <div class="fp_nav"></div>
  <div class="fp_nav"></div>
</div>

<!-- top move button -->
<!-- 클릭시 최상단으로 스크롤 이동 -->
<button type="button" class="fp_top_btn"></button>
```

### example
```html
<body>
  <!-- header -->
  <ul class="fp_menu_wrap">
    <li class="fp_menu" data-fpnum="2"><a href="javascript:void(0)">text</a></li>
    <li class="fp_menu" data-fpnum="2"><a href="javascript:void(0)">text</a></li>
    <li class="fp_menu" data-fpnum="3"><a href="javascript:void(0)">text</a></li>
    <li class="fp_menu" data-fpnum="4"><a href="javascript:void(0)">text</a></li>
  </ul>
  <!-- fullpage -->
  <div class="fp_page_wrap">
    <div class="fp_page">content</div>
    <div class="fp_page">content</div>
    <div class="fp_page">content</div>
    <div class="fp_page">content</div>
    <div class="fp_page">content</div>
  </div>
  <!-- navigation -->
  <ul class="fp_nav_wrap">
    <li class="fp_nav"><a href="#javascript:void(0)"></a></li>
    <li class="fp_nav"><a href="#javascript:void(0)"></a></li>
    <li class="fp_nav"><a href="#javascript:void(0)"></a></li>
    <li class="fp_nav"><a href="#javascript:void(0)"></a></li>
  </ul>
  <!-- top move button -->
  <button type="button" class="fp_top_btn">text</button>
</body>
```
## CSS 관련 설명
### 필수 css파일
layout.css<br/>
reset.css (기존의 reset.css가 있다면 제외)

### layout.css 설정
#### 시간 설정
페이지 스크롤 시간을 자유롭게 설정할 수 있습니다.
```css
.fp_page_wrap {
  /* transition을 설정 하세요 */
  transition: .5s ease-in-out;
}
```

### layout.css 관련 이슈
#### body안에 바로 넣을 경우
기존에 있는 layout.css 그대로 사용.
```html
<body>
  <!-- header -->
  <ul class="fp_menu_wrap">...</ul>
  <!-- fullpage -->
  <div class="fp_page_wrap">...</div>
  <!-- navigation -->
  <ul class="fp_nav_wrap">...</ul>
  <!-- top move button -->
  <button type="button" class="fp_top_btn">...</button>
</body>
```
#### body안을 한번 더 감쌀 경우
```html
<body>
  <div class="wrap">
    <!-- header -->
    <ul class="fp_menu_wrap">...</ul>
    <!-- fullpage -->
    <div class="fp_page_wrap">...</div>
    <!-- navigation -->
    <ul class="fp_nav_wrap">...</ul>
    <!-- top move button -->
    <button type="button" class="fp_top_btn">...</button>
  </div>
</body>
```
layout.css 수정 또는 layout.scss 수정 후 컴파일
```js
/* layout.css */
body {
  overflow: hidden;
}
.wrap {
  height: calc(var(--vh, 1vh) * 100);
  overflow: hidden;
}

/* layout.scss */
body {
	overflow: hidden;
}

.wrap {
	height: calc(var(--vh, 1vh) * 100);
	overflow: hidden;

	.fp_page_wrap {...}
}
```
#### footer 이슈
footer의 경우 화면이 꽉 차지 않는 경우가 대부분 입니다.
```css
/* layout.css */
.fp_page_wrap footer.fp_page {
  height: auto !important;
}

/* layout.css */
.fp_page_wrap {
  .fp_page {....}
  footer.fp_page {
    height: auto !important;
  }
}
```

# JP
[製作のきっかけ](#製作のきっかけ)<br/>
[HTMLの書き方](#HTMLの書き方)<br/>

## 製作のきっかけ
既存に広く知られているfullpageライブラリを商業的に使用するためには費用を支払わなければならない部分がありましたが、これを無料で使用しようとする趣旨で製作することになりました。

## HTMLの書き方
### introduce
```html
<!-- header -->
<!-- data-fpnumプロパティ&値を指定した後、該当ボタンをクリックすると、指定された値と同じページにスクロール移動。 0からスタート -->
<ul class="fp_menu_wrap">
  <li class="fp_menu" data-fpnum="2"></li>
  <li class="fp_menu" data-fpnum="2"></li>
  <li class="fp_menu" data-fpnum="3"></li>
  <li class="fp_menu" data-fpnum="4"></li>
</ul>

<!-- fullpage -->
<div class="fp_page_wrap">
  <div class="fp_page"></div>
  <div class="fp_page"></div>
  <div class="fp_page"></div>
  <div class="fp_page"></div>
  <div class="fp_page"></div>
</div>

<!-- navigation -->
<div class="fp_nav_wrap">
  <div class="fp_nav"></div>
  <div class="fp_nav"></div>
  <div class="fp_nav"></div>
  <div class="fp_nav"></div>
</div>

<!-- top move button -->
<!-- クリックすると最上段にスクロール移動 -->
<button type="button" class="fp_top_btn"></button>
```

### example
```html
<body>
  <!-- header -->
  <ul class="fp_menu_wrap">
    <li class="fp_menu" data-fpnum="2"><a href="javascript:void(0)">text</a></li>
    <li class="fp_menu" data-fpnum="2"><a href="javascript:void(0)">text</a></li>
    <li class="fp_menu" data-fpnum="3"><a href="javascript:void(0)">text</a></li>
    <li class="fp_menu" data-fpnum="4"><a href="javascript:void(0)">text</a></li>
  </ul>
  <!-- fullpage -->
  <div class="fp_page_wrap">
    <div class="fp_page">content</div>
    <div class="fp_page">content</div>
    <div class="fp_page">content</div>
    <div class="fp_page">content</div>
    <div class="fp_page">content</div>
  </div>
  <!-- navigation -->
  <ul class="fp_nav_wrap">
    <li class="fp_nav"><a href="#javascript:void(0)"></a></li>
    <li class="fp_nav"><a href="#javascript:void(0)"></a></li>
    <li class="fp_nav"><a href="#javascript:void(0)"></a></li>
    <li class="fp_nav"><a href="#javascript:void(0)"></a></li>
  </ul>
  <!-- top move button -->
  <button type="button" class="fp_top_btn">text</button>
</body>
```
