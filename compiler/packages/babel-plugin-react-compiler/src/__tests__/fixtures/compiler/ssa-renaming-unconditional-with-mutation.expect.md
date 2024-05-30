
## Input

```javascript
function foo(props) {
  let x = [];
  x.push(props.bar);
  if (props.cond) {
    x = {};
    x = [];
    x.push(props.foo);
  } else {
    x = [];
    x = [];
    x.push(props.bar);
  }
  mut(x);
  return x;
}

```

## Code

```javascript
import { c as _c } from "react/compiler-runtime";
function foo(props) {
  const $ = _c(2);
  let t0;
  if ($[0] !== props) {
    let x = [];
    x.push(props.bar);
    if (props.cond) {
      x = [];
      x.push(props.foo);
    } else {
      x = [];
      x.push(props.bar);
    }

    t0 = x;
    mut(x);
    $[0] = props;
    $[1] = t0;
  } else {
    t0 = $[1];
  }
  return t0;
}

```
      