# Sintaxe Básica

## Tipos de dados primitivos

* Boolean ( true, false)
* Null
* Undefined
* Number (1, 1.2)
* String ("string", 'string')
* Symbol (new in ECMAScript 6)

## var, let, const

## null vs undefined
### undefined
Quando a variavel foi definida mas não setada.

## null
Quando variavel tem valor nulo ou "vazio", não aponta para nenhum tipo ou valor

# NaN
Not-A-Number

Ex:
```javascript
isNaN(NaN);
// true

isNaN(123);
// false

isNaN("string");
// true
```

Ex de variavel não definida:
```javascript
console.log(yyy);
// Uncaught ReferenceError: yyy is not defined
```

Exemplo de variavel definida mas não setada:
```javascript
var string;
console.log(string);
// Retorna undefined
```

Exemplo de variavel setada como null:
```javascript
var foo = null;
console.log(foo);
// Retorna null
```

## Operadores

| Operadores Aritmeticos | Descrição |
| - | - |
| + | Soma ou concatenação de string |
| - | Subratação |
| * | Multiplicação |
| / | Divisão |
| % | Mod ( Resto ) |

| Operadores logicos | Descrição |
| - | - |
| &&, and| E |
| &#124;&#124;, or | Ou |
| ! | Negação |
| ? | Ternario `is_true()? true: false;` |

## Funções úteis

### typeof
Retorno do tipo
```javascript
var string = "valor";
console.log(string.typeof);
```

### console.log
Mostra log no console do navegador
```javascript
var string = "valor";
console.log("valor");
```

## Operador || como atribuidor
Experimente:

`console.log ( null || " user ")`

`console.log (" Karl " || " user ")`
