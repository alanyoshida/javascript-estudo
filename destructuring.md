# Destructuring
No javascript moderno foi introduzido o conceito de Destructuring

```javascript
var a, b, rest;
[a, b] = [1, 2];
console.log(a); // 1
console.log(b); // 2

[a, b, ...rest] = [1, 2, 3, 4, 5];
console.log(a); // 1
console.log(b); // 2
console.log(rest); // [3, 4, 5]

({a, b} = {a:1, b:2});
console.log(a); // 1
console.log(b); // 2

// ES2016 - não implementado em Firefox 47a01
({a, b, ...rest} = {a:1, b:2, c:3, d:4});
```
