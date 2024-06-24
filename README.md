# FullPage
<p>완전 무료의 HTML 친화적인 풀페이지 기능을 만나보세요!<br/>完全無料のHTMLフレンドリーなフルページ機能をご体験ください！</p>

- 풀페이지 / フルページ
- 페이지 내부 컨텐츠 자동 스크롤 / ページ内コンテンツ自動スクロール
- 네비게이션 / ナビゲーション
- 헤더 메뉴 및 페이지 이동 속성 제공 / ヘッダーメニューとページ移動属性を提供
- 탑 버튼 / トップ·ボタン

## Version
current ver1.0.1

## 이 FullPage로 제작된 작업물들을 확인해 보세요!<br/>このFullPageで製作された作業物を確認してみてください！
<a href="https://wonyongwan.github.io/fullpage_intro/index.html" target="blank"><img src="./intro_images/fullPage_main.png" width="100%"/></a>
<a href="https://wonyongwan.github.io/%EB%AA%A8%EB%B9%84%EC%9C%84%EB%93%9C_kbsad_240422/%EB%AA%A8%EB%B9%84%EC%9C%84%EB%93%9C_kbsad_%EC%9D%B8%ED%8A%B8%EB%A1%9C/index.html"><img src="./intro_images/fullPage01.png" width="100%"/></a>


## Language
[KOR](#KOR)<br/>
[JP](#JP)<br/>

# KOR
[제작 계기](#제작-계기)<br/>
[HTML 작성법](#HTML-작성법)<br/>
[CSS 관련 설명](#CSS-관련-설명)<br/>
[Javascript 관련 설명](#Javascript-관련-설명)<br/>

## 제작 계기
기존에 널리 알려져 있는 fullpage 라이브러리를 상업적으로 사용하기 위해서는 비용을 지불해야 하는 부분이 있었는데 이를 무료로 사용하고자 하는 취지에서 제작하게 되었습니다.

## HTML 작성법
### introduce
fp_page_wrap는 필수. 나머지는 선택
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
<!-- example -->
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
<!-- example -->
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
#### footer height 값
footer의 경우 화면이 꽉 차지 않는 경우가 대부분 입니다. height값을 auto로 변경 해주세요.
```css
/* layout.css */
.fp_page_wrap footer.fp_page {
  height: auto !important;
}

/* layout.scss */
.fp_page_wrap {
  .fp_page {....}
  footer.fp_page {
    height: auto !important;
  }
}
```

## Javascript 관련 설명
현재 module type만을 지원 합니다. 추후 text type을 지원할 예정입니다.
```html
<!-- 꼭 type="module"을 명시 해주세요 -->
<script type="module" src="./js/main.js"></script>
```

### 당신이 사용할 수 있는 값
pageCount, pageWrapTime
```js
// main.js
import { fullPageEffect, fullResize, topBtnFlag, menuFlag, navFlag, specificFlag, pageCount, pageWrapTime } from './fullPage.js';
```
pageCount: 현재 위치하고 있는 페이지의 index값을 가져옵니다.
pageWrapTime: 당신이 지정한 transition의 값을 가져옵니다. 


# JP
[製作のきっかけ](#製作のきっかけ)<br/>
[HTMLの書き方](#HTMLの書き方)<br/>
[CSSに関する説明](#CSSに関する説明)<br/>
[Javascriptに関する説明](#Javascriptに関する説明)<br/>

## 製作のきっかけ
既存に広く知られているfullpageライブラリを商業的に使用するためには費用を支払わなければならない部分がありましたが、これを無料で使用しようとする趣旨で製作することになりました。

## HTMLの書き方
### introduce
fp_page_wrapは必須。あとは選択
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
## CSSに関する説明
### 必須cssファイル
layout.css<br/>
reset.css (既存のreset.cssがあれば除外)

### layout.css設定
#### 時間設定
ページスクロールの時間を自由に設定できます。
```css
.fp_page_wrap {
  /* transitionを設定してください */
  transition: .5s ease-in-out;
}
```

### layout.css関連イシュー
#### bodyの中にすぐ入れる場合
既存のlayout.cssをそのまま使用。
```html
<!-- example -->
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
#### bodyの中をもう一度包み込む場合
```html
<!-- example -->
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
layout.css修正またはlayout.scss修正後のコンパイル
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
#### footer height値
footerの場合、画面がいっぱいにならない場合がほとんどです。 height値をautoに変更してください。
```css
/* layout.css */
.fp_page_wrap footer.fp_page {
  height: auto !important;
}

/* layout.scss */
.fp_page_wrap {
  .fp_page {....}
  footer.fp_page {
    height: auto !important;
  }
}
```

## Javascriptに関する説明
現在module typeのみをサポートしています。 今後text typeに対応する予定です。
```html
<!-- 必ず type="module"を明示してください -->
<script type="module" src="./js/main.js"></script>
```

### あなたが使える値
pageCount, pageWrapTime
```js
// main.js
import { fullPageEffect, fullResize, topBtnFlag, menuFlag, navFlag, specificFlag, pageCount, pageWrapTime } from './fullPage.js';
```
pageCount: 現在位置しているページのindex値を取得します。
pageWrapTime: あなたが指定したtransitionの値を取得します。
