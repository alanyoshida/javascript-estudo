# Estruturas de dados
## Map
O objeto Map é um mapa simples de chave/valor. Qualquer valor (objeto e valores primitivos) pode ser usado como uma chave ou um valor.

[Documentação](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Map)

Exemplo:

```javascript
var myMap = new Map();

var keyString = "uma string",
    keyObj = {},
    keyFunc = function () {};

// configurando os valores
myMap.set(keyString, "valor associado com 'uma string'");
myMap.set(keyObj, "valor associado com keyObj");
myMap.set(keyFunc, "valor associado com keyFunc");

myMap.size; // 3

// obtendo os valores
myMap.get(keyString);    // "valor associado com 'uma string'"
myMap.get(keyObj);       // "valor associado com keyObj"
myMap.get(keyFunc);      // "valor associado com keyFunc"

myMap.get("uma string"); // "valor associado com 'uma string'"
                         // pois keyString === 'uma string'
myMap.get({});           // undefined, pois keyObj !== {}
myMap.get(function() {}) // undefined, pois keyFunc !== function () {}
```

## Set

O objeto Set permite que você armazene valores únicos de qualquer tipo, desde valores primitivos a referências a objetos.

[Documentação](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Set)

Exemplo:

```javascript
var mySet = new Set();

mySet.add(1);
mySet.add(5);
mySet.add("some text");

mySet.has(1); // true
mySet.has(3); // false, 3 não foi adicionado ao set (Conjunto)
mySet.has(5);              // true
mySet.has(Math.sqrt(25));  // true
mySet.has("Some Text".toLowerCase()); // true

mySet.size; // 3

mySet.delete(5); // remove 5 do set
mySet.has(5);    // false, 5 já foi removido

mySet.size; // 2, nós simplesmente removemos um valor
```

## WeakMap

O objeto WeakMap é uma coleção de pares key/value no qual as chaves são objetos e os valores podem ser valores arbitrários.

[Documentação](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/WeakMap)

```javascript
var wm1 = new WeakMap(),
    wm2 = new WeakMap(),
    wm3 = new WeakMap();
var o1 = {},
    o2 = function(){},
    o3 = window;

wm1.set(o1, 37);
wm1.set(o2, "azerty");
wm2.set(o1, o2); // um valor pode ser qualquer coisa, incluindo um objeto or uma função
wm2.set(o3, undefined);
wm2.set(wm1, wm2); // chaves e valores pode ser quaisquer objetos. Até mesmo WeakMaps! :O

wm1.get(o2); // "azerty"
wm2.get(o2); // undefined, pois não existe valor para o2 em wm2 
wm2.get(o3); // undefined, pois este é o valor definido

wm1.has(o2); // true
wm2.has(o2); // false
wm2.has(o3); // true (mesmo se o valor armazenado for 'undefined')

wm3.set(o1, 37);
wm3.get(o1); // 37
wm3.clear();
wm3.get(o1); // undefined, pois wm3 foi 'limpado' e não há mais valor para o1.

wm1.has(o1);   // true
wm1.delete(o1);
wm1.has(o1);   // false
```

## WeakSet

O objeto WeakSet pertmite que você armazene objetos mantidos “fracamente” na coleção.

[Documentação](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/WeakSet)

```javascript
var ws = new WeakSet();
var obj = {};
var foo = {};

ws.add(window);
ws.add(obj);

ws.has(window); // true
ws.has(foo);    // false, foo não foi adicionado ao set

ws.delete(window); // remove window do set 
ws.has(window);    // false, window foi removido
```