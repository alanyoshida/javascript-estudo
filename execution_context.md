# Syntax parser

Valida a sua gramatica e determina o que ele faz.

# Lexical Environment

Onde você roda seu codigo.

Ex variavel dentro de funcao:
```javascript
function hello_world(){
  var a = "Hello World";
  console.log(a);
}
```

Ex variavel fora da funcao:
```javascript
var a = "Hello World";
function hello_world(){
  console.log(a);
}
```

# Execution Context

O **Execution Context** é o **wrapper** que gerencia os varios **Lexical Environments** rodando.

## Global Execution Context

Cria o **Global Object** e o **this**

Global Object = **window**

**this** aponta para **window**

Toda variavel ou funcão criada fora de qualquer função vira global.

Ex:

```javascript
var a = "Hello World"
function b(){}

console.log(a); // No escopo global
console.log(window.a); // Dentro do objeto do escopo global
console.log(window.b);
```

No caso de variaveis globais não existe **Lexical Environment** externa.

