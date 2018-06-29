# Try Catch

As declarações try...catch marcam um bloco de declarações para testar (try),  e especifica uma resposta, caso uma exceção seja lançada.

[Documentação](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/try...catch)

```javascript
try {
   throw "myException"; // gera uma exceção
}
catch (e) {
   // declarações para manipular quaisquer exceções
   logMyErrors(e); // passa o objeto de exceção para o manipulador de erro
}
```

```javascript
try {
    myroutine(); // pode lançar três tipos de exceções
} catch (e if e instanceof TypeError) {
    // declarações para manipular exceções TypeError
} catch (e if e instanceof RangeError) {
    // declarações para manipular exceções RangeError
} catch (e if e instanceof EvalError) {
    // declarações para manipular exceções EvalError
} catch (e) {
    // declarações para manipular quaisquer exceções não especificadas
    logMyErrors(e); // passa o objeto de exceção para o manipulador de erro
}
```

## Finally

```javascript
try {
  try {
    throw new Error("oops");
  }
  finally {
    console.log("finally");
  }
}
catch (ex) {
  console.error("outer", ex.message);
}

// Resultado
// "finally"
// "outer" "oops"
```

