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