# Iterators

## For

A instrução for cria um loop que consiste em três expressões opcionais, dentro de parênteses e separadas por ponto e vírgula, seguidas por uma declaração ou uma sequência de declarações executadas em sequência.

[Documentação](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/for)

```javascript
let iterable = [10, 20, 30];

for (var i = 0; i < iterable.length; i++) {
   console.log(iterable[i]);
   // more statements
}
```

## For of

O loop **for...of** percorre objetos iterativos (incluindo Array, Map, Set, o objeto arguments e assim por diante), chamando uma função personalizada com instruções a serem executadas para o valor de cada objeto distinto.

[Documentação](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/for...of)

```javascript
let iterable = [10, 20, 30];

for (let value of iterable) {
  console.log(value);
}
```

## For in

O laço **for...in**  interage sobre propriedades enumeradas de um objeto, na ordem original de inserção.  O laço pode ser executado para cada propriedade distinta do objeto.

[Documentação](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/for...in)

```javascript
//Objeto
var obj = {a:1, b:2, c:3};

//Para prop (propriedade) in obj (objeto) faça
for (var prop in obj) {
  // ctrl+shift+k (para abrir o console no mozilla firefox)
  console.log("obj." + prop + " = " + obj[prop]);
}

// A saída (output) deverá ser:
// "obj.a = 1"
// "obj.b = 2"
// "obj.c = 3"
```