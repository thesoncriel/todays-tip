# 오늘의 웹표준 - button 과 anchor 의 올바른 쓰임새

우린 종종 웹프론트 개발 시 사용자의 클릭 이벤트 등을 받아내기 위해 &lt;div&gt; 혹은 &lt;span&gt; 을 사용하곤 합니다.

그런데 그거 아십니까?

저렇게 쓰는것은 웹표준에 벗어나는 방법 입니다!

## 옛날 이야기

오래된 예기를 하나 하겠습니다.

때는 IE6~8이 창궐(?)하던 2000년대 중반. 수많은 웹디자이너와 웹개발자들은 버튼에 원하는 스타일을 넣기 위해 안간힘을 썼습니다.

처음엔 이렇게 했습니다.

```html
<button class="btn">나 버튼 ㅎ</button>
```

그러나 저 button 요소에는 window 환경에서 기본 제공해 주는 회색 빛깔의 멋없는 기본 스타일이 먹혀져 있었으며,
나쁜점은 그 스타일을 저 button 요소를 대상으로 직접 바꾸는게 불가능 했다는 것입니다!

그래서 이 후 이렇게 바꾸게 됩니다.

```html
<span class="btn">
  <button>나 버튼 ㅎ</button>
</span>
```

이렇게 하면 span 요소에 원하는 디자인을 입히고, button 요소는 오직 클릭 가능 영역만 보이도록 한 것입니다.

당시엔 이게 최선이었죠.

헌데 굳이 저렇게 2단으로 요소를 중첩 시키지 않아도 버튼 요소처럼 동작되는 요소가 따로 더 있었습니다.

바로 &lt;a&gt; 태그, anchor 입니다.

```html
<a href="#" class="btn">
  나 버튼 ㅎ
</a>
```

수많은 사람들이 anchor 를 기본 기능인 페이지 이동, 즉 하이퍼 링크(hiper-link) 기능을 무시하고 마구 사용하기 시작합니다!

거기다 웹표준에 따르면 native keyboard 의 tab index 도 가능하니 웹접근성도 얻는 등 입맛돋는 요소였음엔 분명 했습니다.

하지만 anchor 는 분명 링크 기능을 제공하는 요소 입니다.

알지만 잘못쓰고 있었죠. 이유는? 대안이 없었기 때문입니다. 버튼에 스타일이 안먹혔어요 ㅠ.ㅠ

## 클릭이 필요하면 &lt;button&gt; 을 쓰세요

하지만 시대가 변하고 button 요소도 마음껏 style customizing 이 가능한 세상이 왔습니다!

굳이 div, span 에 버튼 스타일을 넣고 버튼 행세를 하지 않아도 되는 것입니다.

버튼은 이럴 때 쓰세요!

- 현재 페이지를 벗어나지 않고 사용자와의 의사소통 (interaction)을 할 때
- 말 그대로 버튼을 사용해야 할 때

## 링크가 필요하면 &lt;a&gt; 를 쓰세요

button 처럼 생겼지만 다른 페이지로 가는 등 링크의 성질을 가진 개체가 있습니다.

아래와 같은 상황일 때는 anchor 를 쓰세요.

- 클릭 시 다른 페이지나 route 로 이동
- tab 이나 modal 을 여는 용도인데, history 관리를 별도로 하여 뒤로가기 등의 웹브라우저 액션에 의하여 이전에 선택했던 tab 이나 열렸던 modal이 닫혀야 할 때

## 참고 문헌

- [links are not buttons neither are divs and spans](https://karlgroves.com/2013/05/14/links-are-not-buttons-neither-are-divs-and-spans)
- [W3.org - DOM Level 2: Base HtmlElement Interface](https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-011100101)
