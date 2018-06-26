# Symbols

O symbol é um tipo de dado único e imutável e pode ser usado como um identificador para propriedades de objeto.

```javascript
const UnicSymbol1 = Symbol();
const UnicSymbol2 = Symbol();


const object = {};
object[UnicSymbol1] = 'Teste 1';
object[UnicSymbol2] = 'Teste 2';

console.log(object[UnicSymbol1]);
console.log(object[UnicSymbol2]);

Object.getOwnPropertySymbols(object)
    .forEach(symbol => console.log(object[symbol]));
```