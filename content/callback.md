# Callbacks

```javascript

function funcao(parametro, callback){
  if (typeof callback === "function")
    return callback(parametro);
}

funcao(123, function(param){
  return param + param;
});

// Retorna: 246
```
