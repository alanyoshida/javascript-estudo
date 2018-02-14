## Call
O método call() invoca uma função com um dado valor this  e argumentos passados individualmente.

```javascript
function Product(name, price) {
  this.name = name;
  this.price = price;

  if (price < 0) {
    throw RangeError('Cannot create product ' +
                      this.name + ' with a negative price');
  }

  return this;
}

function Food(name, price) {
  Product.call(this, name, price);
  this.category = 'food';
}

Food.prototype = Object.create(Product.prototype);

function Toy(name, price) {
  Product.call(this, name, price);
  this.category = 'toy';
}

Toy.prototype = Object.create(Product.prototype);

var cheese = new Food('feta', 5);
var fun = new Toy('robot', 40);
```

## bind

O método bind() cria uma nova função que, quando chamada, tem seu parâmetro (ref mesmo objeto) this, podendo vincular ou iniciar com outros parâmetros definidos, dada sequência dos argumentos que foram fornecidos quando a nova função é chamada.

```javascript
this.x = 9; 
var module = {
  x: 81,
  getX: function() { return this.x; }
};

module.getX(); // 81

var getX = module.getX;
getX(); // 9,  porque, neste caso, "this" refere-se ao objeto global 

// Criando uma nova função com 'this' vinculada ao módulo
var boundGetX = getX.bind(module);
boundGetX(); // 81
```

## apply

O método apply() chama uma função com um dado valor this e argumentos providos como um array (ou um objeto parecido com um array).

```javascript
var person = {
    firstName:"John",
    lastName: "Doe",
    fullName: function() {
        return this.firstName + " " + this.lastName;
    }
}
var myObject = {
    firstName:"Mary",
    lastName: "Doe",
}
person.fullName.apply(myObject);  // Will return "Mary Doe"
```

```javascript
Math.max.apply(null,[1,2,3]); // Will also return 3
```

### "monkey-patching"
```javascript
var originalfoo = someobject.foo;
someobject.foo = function() {
  // Faça coisas antes de chamar a função
  console.log(arguments);
  // Chama a função como se ela estivesse sido chamada normalmente:
  originalfoo.apply(this, arguments);
  // Rode as coisas que vem depois, aqui.
}
```