# Sintaxe Básica

## Tipos de dados primitivos

* Boolean ( true, false)
* Null
* Undefined
* Number (1, 1.2)
* String ("string", 'string')
* Symbol (new in ECMAScript 6)

# String

Strings são cadeias de caracteres.

```javascript
var nome = "Joao Ninguem";
console.log(nome[2]);
// Result: e
```

## var, let, const

### var
Declaração de uma variável. Caso uma variavel 

```javascript
var x = 1;

if (x === 1) {
  var x = 2;

  console.log(x);
  // expected output: 2
}

console.log(x);
// expected output: 2
```

### let
Variaveis com let tem seu escopo par o bloco onde foram definidas.

```javascript
let x = 1;

if (x === 1) {
  let x = 2;

  console.log(x);
  // expected output: 2
}

console.log(x);
// expected output: 1
```

### const
Variaveis declaradas com const não podem ser reatribuida ou redeclarada.

Constantes podem ser globais ou locais, a constante global não é atribuida ao objeto **window**.

A constante não significa que o valor é imutável, mas que não pode ser reatribuida.

Não pode ter uma função ou variavel com mesmo nome no mesmo escopo

```javascript
const number = 42;

try {
  number = 99;
} catch(err) {
  console.log(err);
  // expected output: TypeError: invalid assignment to const `number'
  // Note - error messages will vary depending on browser
}

console.log(number);
// expected output: 42
```

O uso de const com objetos:
```javascript
// Cria objeto
const MY_OBJECT = {'key': 'value'};

// Tentandos sobrescrever a constante retorna o erro - Uncaught TypeError: Assignment to constant variable.
MY_OBJECT = {'OTHER_KEY': 'value'};

// As chaves do objeto não são protegidas
// Então o codigo abaixo é executado sem problema
MY_OBJECT.key = 'otherValue'; // Use Object.freeze() to make object immutable
```

## null vs undefined

### undefined
Undefined significa que uma variavel foi declarada, mas não tem nenhum valor setado.

```javascript
var test;
console.log(test);
// Result: undefined
```

### null
O null é um valor que pode ser passado para uma variavel.

Quando variavel tem valor nulo ou "vazio", não aponta para nenhum tipo ou valor

Você pode colocar em suas variaveis o **null** para definir que não tem valor ainda, assim podera saber se você setou a variavel, ou se for **undefined** não foi nem setada.

```javascript
var test;
test = null;
console.log(test);
// Result: null
```

**Atenção:** `typeof null === "object"`

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

## Switch/Case
Boa pratica do uso do Switch, use ao inves de varios if else.

```javascript
function getCategory(age) {  
    var category = "";  
    switch (true) {  
        case isNaN(age):  
            category = "not an age";  
            break;  
        case (age >= 50):  
            category = "Old";  
            break;  
        case (age <= 20):  
            category = "Baby";  
            break;  
        default:  
            category = "Young";  
            break;  
    };  
    return category;  
}  
getCategory(5);  // will return "Baby"
```

## Eval
Não é uma boa pratica usar o eval.

Referencia: http://2ality.com/2014/01/eval.html

```javascript
var obj = {
  prop1: '123', prop2: 'abc'
}

// Caso precise descobrir o nome de uma propriedade em tempo de execução
// Ao inves de usar isso:
var value = eval('obj.'+propName);

// Use isso:
var value = obj[propName];
```

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

# Debugger
Experimente:

```javascript
function bug() {
  debugger;
  console.log('ant')
}
```