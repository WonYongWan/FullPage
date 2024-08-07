## Save Version
ver1.0.0 <br>
ver1.0.1 <br>
```js
issue contents
첫번째(top), 마지막(bottom) 페이지에서 한 방향 스크롤 연속 후 메뉴 클릭 후 한 방향 스크롤 다시 할 경우 한꺼번에 첫번째(top), 마지막(bottom) 페이지로 이동하는 현상 개선 작업
```
ver1.1.1
```js
issue contents
메뉴 클릭시 스크롤이 있는 컨텐츠들 scrollTop = 0으로 설정 작업
```
<strong>current</strong> ver1.1.2
```js
issue contents
getComputedStyle().transition의 배열 순서가 바뀜 문제 개선 작업

// (before)
export const pageWrapTime = Number(getComputedStyle($pageWrap).transition.split(" ")[1].replace('s', '') * 1000);
// (after)
export const pageWrapTime = Number(getComputedStyle($pageWrap).transition.replace(/([^0-9.])/g, '') * 1000);
```
