# jQeury

## Basic structure

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>JS Bin</title>

  <script src="https://code.jquery.com/jquery-1.6.4.js"></script>
  <script>
    $(document).ready(function() {
      alert("안녕하세요, jQuery에 온 걸 환영합니다.");
    });
  </script>
</head>

<body>
  test
</body>

</html>
```

## `ready`

```javascript
$( document ).ready(() => {
  ...
});
```

## Lesson 2 : Effects

- Basic
  - `.hide()`
  - `.show()`
  - `.toggle()`
- Fade
  - `.fadeOut()`
  - `.fadeIn()`
  - `.fadeToggle()`
- Slide
  - `.slideUp()`
  - `.slideDown()`
  - `.slideToggle()`

## Lession 4 : Style Method

- The `.css()` method can change style- properties of an element.
- The `.css()` method can accept multiple- styles at once if you pass it a JavaScript object as its argument.
- The `.animate()` method can change- specific style properties over a period of time.
- The `.addClass()` will add a CSS class to- an element, and the `removeClass()` method will remove a CSS class.
- The `.toggleClass()` method will toggle a- class on or off an element
