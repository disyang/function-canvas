## 🔌 Canvas

### rect-radius
Creates a function that accepts up to `7` arguments, `x` is x coordinate, `y` is y coordinate, `w` is width, `h` is height, `r` is radius, `c` is color, `context` is canvas's context. Creates a rect with radius.

```js
function rect(x, y, w, h, r = 0, c = '#000', context) {
  context.beginPath();
  context.fillStyle = c;
  if(r === 0) context.fillRect(x, y, w, h);
  else {
    context.moveTo(x, y + r);
    context.arcTo(x, y, x + r, y, r);
    context.lineTo(x + w - r, y);
    context.arcTo(x + w, y, x + w, y + r, r);
    context.lineTo(x + w, y + h - r);
    context.arcTo(x + w, y + h, x + w - r, y + h, r);
    context.lineTo(x + r, y + h);
    context.arcTo(x, y + h, x, y + h - r, r);
    context.closePath();
    context.fill();
  }
}
```
<details>
<summary>Examples</summary>

```js
    const canvas = document.querySelector('canvas');
    const context = canvas.getContext('2d');
    rect(10, 10, 100, 50, 5, '#409EFF', context);
```

</details>

<br>[⬆ Back to top](#contents)
