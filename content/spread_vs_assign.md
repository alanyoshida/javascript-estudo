# Spread Operator VS Object Assign

```javascript
// 1
(function first() {
  var a = { b: 2, c: 3, d: 4 };
  var b;

  b = Object.assign({}, a);

  console.log("first a", a);
  console.log("first b", b);
  console.log("A === B ", a===b);
  console.log("=====================");
})();

// 2
(function second() {
  var a = { b: 2, c: 3, d: 4 }
  var b;

  b = { ...a };

  console.log("second a", a);
  console.log("second b", b);
  console.log("A === B ", a===b);
  console.log("=====================");
})();

// 3
(function third() {
  var a = { b: 2, c: 3, d: 4 }
  var b;

  ({ ...b } = a);

  console.log("third a", a);
  console.log("third b", b);
  console.log("A === B ", a===b);
  console.log("=====================");
})();

// 4
(function fourth() {
  var a = { b: 2, c: 3, d: 4 }
  var b = {};

  Object.assign(b, a);

  console.log("fourth a", a);
  console.log("fourth b", b);
  console.log("A === B ", a===b);
  console.log("=====================");
})();

//5
(function fifth() {
  var a = { b: 2, c: 3, d: 4 };
  var b;

  b = a;

  console.log("fifth a", a);
  console.log("fifth b", b);
  console.log("A === B ", a===b);
})();
```