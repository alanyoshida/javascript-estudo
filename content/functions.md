# Funções

## ES5
```javascript
function funcao(){
  // Codigo aqui ...
}
```

```javascript
var funcao = function(){
  // Codigo aqui ...
}
```

### Função Anonima
```javascript
function(){
  alert("Hello");
}

// Ex:
setTimeout(function(){
  alert("Hello");
}, 3000);
```

## ES6

# Arrow  
```javascript
() => {
  // Codigo aqui ...
}

// Ex:
setTimeout( () => {
  alert("Hello");
}, 3000);
```

### Função Anonima

#### Uma linha usando Arrow Function
```javascript
(parametro1, parametro2) =>  parametro + parametro2
```

#### Uma linha usando Arrow Function
```javascript
() =>  blabla();
```

#### Mais de uma linha usando Arrow Function
```javascript
() =>  {
  // Seu codigo aqui
}
```


# Diferenças entre funcão Anonima e Arrow Function

Função anonima gera novo contexto de execução, ou seja escopo.

Arrow function aproveita o escopo externo.
