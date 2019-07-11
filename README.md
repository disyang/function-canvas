## 🔌 Adapter

### rect radius
Creates a function that accepts up to `7` arguments, `x` is x coordinate, `y` is y coordinate, `w` is width, `h` is height, `r` is radius, `c` is color, `context` is canvas's context. Creates a rect with radius.

Call the provided function, `fn`, with up to `7` arguments, using 
```js
const ary = (fn, n) => (...args) => fn(...args.slice(0, n));
```
