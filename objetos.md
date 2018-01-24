# Objetos
```javascript
var a = new Object();
var b = Object.create(null);
var c = {};
```

## Function Expressions
```javascript
// Construtor
var Obj = function(name) { // Função anonima
  this.name = name
}
var c = new Obj("hello"); 
```

## Function Declarations
```javascript
function Objeto(){};
var obj = new Objeto();
```

## Usando prototype
```javascript
function myObj(){};
myObj.prototype.name = "hello";
var k = new myObj();
```

## ES6
```javascript
class myObject  {
  constructor(name) {
    this.name = name;
  }
}
var e = new myObject("hello");
```

## Singleton
```javascript
var l = new function(){
  this.name = "hello";
}
```
