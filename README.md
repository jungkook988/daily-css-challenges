# daily-css-challenges

### 2022/12/27

> easy-coderain-login

- display: flex; gap: 40px;
- pointer-events: none;
- input: required -> input:focus, input:valid;

### 2022/12/28

> easy-delta-border

- width: 0; height: 0;
- border: solid 100px color;
- border-color: transparent;
- border-top-color: red;

### 2022/12/29

> easy-circle-audi

- position: absolute; inset: -25px;
- ::before -> z-index: 100;
- ::after -> z-index: 1;
- ::after -> filter: blur(15px);

### 2022/12/30

> esay-input-colorline

- animation + transition
- background-position-x
- background-position-y

### 2023/1/1

> easy-scroll-snap

- scroll-snap-type: mandatory | proximity
- scroll-snap-align: start | center | end
- scroll-padding: px

### 2023/1/2

> easy-svg-line-animation

- stroke-dasharray
- stoke-dashoffset
- fill

### 2023/1/3

> easy-svg-multiLine-animation

- svg -> <symbol id="text"><text>123</text></symbol>
- svg -> <use href="#text"></use>
- text:nth-of-type();
- animation-delay: -1.2s;

### 2023/1/4

> easy-ios-switch

- input/type=checkbox -> input:checked
- input:checked::before -> left: calc(100% - 36px);

### 2023/1/5

> easy-rotateline-login

- linear-gradient(deg, $color1, $color2 ...)
- transform-origin: bottom right;
- animation-delay: -3s;
- inset: 2px;

### 2023/1/6

> easy-musicline-loading

- grid
- animation-delay

### 2023/1/7

> easy-clip

- border-radius
- clip-path: polygon
- clip-path: url(svg-id)

### 2023/1/8

> medium-new-year

- transform-style: preserve-3d;
- `<span style="--i: 1;">` -> transform: rotateY(calc(90deg \* var(--i)));
- `<span data-text="text">` -> content: attr(data-text);
- filter
- - blur();
- - drop-shadow();
- -webkit-text-stroke: 3px #000; // archive

### 2023/1/9

> medium-scan-qrcode

- filter: drop-shadow() drop-shadow() ...
- animation: animate setp(1) infinite;

### 2023/1/10

> medium-bubble-animate

- box-shadow: inset 0 0 25px rgba(255, 255, 255, 0)
- filter: blur(2px);
- zoom: 0.5;

### 2023/1/11

> medium-typing

- font-family: monospace; // 字符等宽
- width: 1ch; // 1 字符宽度,配合 monospace 使用
- animation: second animate steps(2, jump-none) infinite; // steps 函数
- h1.animate span // 当 h1 标签拥有 animate 样式时，span 会做出什么动作

```javascript
h1.textContent.replace(/\S/g, "<span>$&</span>") // 转成span
h1.addEventListener("animationend" e => {
    if (e.target === document.querySelector("h1 span:last-child")) {
        h1.classList.add("ended");
    }
})
```

### 2023/1/12

> medium-title

```javascript
const h1 = document.querySelector("h1");
h1.innerHTML = h1.textContent.replace(/\S/g, "<span>$&</span>"); // 转成span

document.querySelectorAll("h1 > span").forEach((span, index) => {
  span.style.setProperty("--delay", `${index * 0.1}s`); // 添加动画延时
});

document.querySelectorAll("button").forEach((button) => {
  button.addEventListener("click", (e) => {
    // 设置动画名变量
    h1.style.setProperty(
      "--animation",
      e.target.getAttribute("data-animation")
    );
    h1.classList.remove("animate");
    void h1.offsetWidth; // 强制浏览器 Reflow，否则无法点击2次
    h1.classList.add("animate");
  });
});
```
