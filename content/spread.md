# Spread Operator

O  operador spread permite uma expressão ser expandida em locais onde múltiplos argumentos (por chamadas de função) ou múltiplos elementos (por array literais) são esperados.

```javascript
function minhaFuncao(x, y, z) { }
var args = [0, 1, 2];
minhaFuncao(...args);
```

```javascript
function minhaFuncao(v, w, x, y, z) { }
var args = [0, 1];
minhaFuncao(-1, ...args, 2, ...[3]);
```
