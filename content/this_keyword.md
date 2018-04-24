# Palavra chave **this**

```javascript
var test = {
  prop: 42,
  func: function() {
    return this.prop;
  },
};

console.log(test.func());
// expected output: 42
```

### Contexto Global

```javascript
// In web browsers, the window object is also the global object:
console.log(this === window); // true
```

### Com Strict mode

```javascript
function f2() {
  'use strict'; // see strict mode
  return this;
}

f2() === undefined; // true
```

### Sem Strict Mode

```javascript
function f1() {
  return this;
}

// In a browser:
f1() === window; // true 

// In Node:
f1() === global; // true
```

### Bind

```javascript
function f() {
  return this.a;
}

var g = f.bind({a: 'azerty'});
console.log(g()); // azerty

var h = g.bind({a: 'yoo'}); // bind only works once!
console.log(h()); // azerty

var o = {a: 37, f: f, g: g, h: h};
console.log(o.f(),o.f(), o.g(), o.h()); // 37,37, azerty, azerty
```

### Arrow functions

```javascript
var globalObject = this;
var foo = (() => this);
console.log(foo() === globalObject); // true

// Call as a method of an object
var obj = {func: foo};
console.log(obj.func() === globalObject); // true

// Attempt to set this using call
console.log(foo.call(obj) === globalObject); // true

// Attempt to set this using bind
foo = foo.bind(obj);
console.log(foo() === globalObject); // true
```

No matter what, foo's this is set to what it was when it was created

```javascript
var obj = {
  bar: function() {
    var x = (() => this);
    return x;
  }
};

var fn = obj.bar();

console.log(fn() === obj); // true

var fn2 = obj.bar;

// Then calling the arrow function this is equals to window because it follows the this from bar.
console.log(fn2()() == window); // true
```