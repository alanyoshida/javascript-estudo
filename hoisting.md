# Hoisting

Ex:

```javascript
var a = "Hello World"

function b(){
  console.log("B chamado");
}

console.log(a);
b();
```

### Resultado:
`Hello World`

`B chamado`

```javacript
console.log(a);
b();

var a = "Hello World"

function b(){
  console.log("B chamado");
}
```

### Resultado:
`undefined`

`B chamado`

```javacript
console.log(a);
b();

// Removendo a linha abaixo
// var a = "Hello World"

function b(){
  console.log("B chamado");
}
```

### Resultado:
`Uncaught ReferenceErrr: a is not defined`

`B chamado`

# Fase de criação do **Execution Context**
O **Execution Context** passa pelo codigo e encontra as declarações de variaveis, funcoes, objetos
e reserva espaço em memoria para elas.

Ele tambem seta todas as variaveis como **undefined** nessa etapa.

Isso é o **Hoisting**.

Exemplo de como as variaveis são setadas como undefined:

```javascript
console.log(a);
```

```javascript
var a;
console.log(a);
```

# Fase de execução
Passa linha por linha executando o codigo e setando os valores reais das variaveis.
