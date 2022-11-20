---
title: Distance between two points
tags: math,algorithm
expertise: beginner
cover: blog_images/measuring.jpg
author: pauluzo
firstSeen: 2022-12-20T15:31:31+01:00
---

- Given three points(coordinates), calculate if the triangle formed by those points has a positive area.

```js
const nonDegenerate = (x0, y0, x1, y1, x2, y2) => {
  const lineA = Math.hypot(x1 - x0, y1 - y0);
  const lineB = Math.hypot(x2 - x1, y2 - y1);
  const lineC = Math.hypot(x2 - x0, y2 - y0);

  if(lineA + lineB > lineC && lineB + lineC > lineA && lineC + lineA > lineB) {
    return true;
  }

  return false;
}
```

```js
nonDegenerate(1, 1, 3, 4, 4, 6) // true
nonDegenerate(1, 1, 5, 1, 2, 1) // false
```
