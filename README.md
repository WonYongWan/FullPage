# FullPage
current ver1.0.0

## Language
[KOR](#KOR)<br/>
[JP](#JP)<br/>

# KOR
[제작 계기](#제작-계기)<br/>
[HTML 작성법](#HTML-작성법)<br/>

## 제작 계기
기존에 널리 알려져 있는 fullpage 라이브러리를 상업적으로 사용하기 위해서는 비용을 지불해야 하는 부분이 있었는데 이를 무료로 사용하고자 하는 취지에서 제작하게 되었습니다.

## HTML 작성법
### introduce
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
