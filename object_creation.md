# Objetos
```javascript
// Objetos vazios
var a = new Object();
var b = Object.create(null);
var c = {};

// Objeto com atributo e "metodo"
var d = {
  atributo: 'valor',
  metodo: function(){
    console.log(this.atributo);
  }
};
```

## Function Expressions
```javascript
// Construtor
var Obj = function(name) { // Função anonima
  this.name = name; // atributo
}
var c = new Obj("hello");
```

## Function Declarations
```javascript
// Cria Funcao
function Objeto(){};

// Instanciacao, toda função pode virar objeto
var obj = new Objeto();
```

## Usando prototype
```javascript
function Objeto(){};

// Atributo
Objeto.prototype.name = "hello";

// Method
Objeto.prototype.method_1 = function(){
  // Code here ...
}



// Instanciacao
var k = new Objeto();
```

## ES6
```javascript
class myObject  {
  constructor(name) {
    this.name = name;
  }
  method_1(){
    // Code here ...
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
