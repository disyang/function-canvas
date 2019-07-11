## 🔌 Canvas

### rect-radius
Creates a function that accepts up to `7` arguments, `x` is x coordinate, `y` is y coordinate, `w` is width, `h` is height, `r` is radius, `c` is color, `context` is canvas's context. Creates a rect with radius.

Call the provided function `rect`, with up to `7` arguments, using 
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
Promise.resolve([1, 2, 3])
  .then(call('map', x => 2 * x))
  .then(console.log); // [ 2, 4, 6 ]
const map = call.bind(null, 'map');
Promise.resolve([1, 2, 3])
  .then(map(x => 2 * x))
  .then(console.log); // [ 2, 4, 6 ]
```

</details>
<br>[⬆ Back to top](#contents)
