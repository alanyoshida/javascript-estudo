# Atributos e metodos privados em objetos

```javascript
var MinhaClasse = (function(){

  var variavelPrivada1 = null;
  var variavelPrivada2 = null;

  objeto = function (var1, var2) {
    var self = this;

    self.variavelPublica1 = var1; 
    self.variavelPublica2 = var2;
  }

  objeto.prototype = {
    metodoPublico1: function(){
      return metodoPrivado1();
    },
    metodoPublico2: function(){
      return metodoPrivado2();
    },
    metodoPublico3: function(){
      return metodoPrivado3();
    },
    setVariavelPrivada1: function (var1) {
      variavelPrivada1 = var1;
    },
    getVariavelPrivada1: function () {
      return variavelPrivada1;
    }
  }

  var metodoPrivado1 = function(){
    return "retorno de metodoPrivado1";
  }
  var metodoPrivado2 = function(){
    return "retorno de metodoPrivado2";
  }
  var metodoPrivado3 = function(){
    return "retorno de metodoPrivado3";
  }

  return objeto;

})()

var meuObjeto = new MinhaClasse("teste1", "teste2");
console.log("MeuObjeto", meuObjeto);

console.log("metodoPublico1", meuObjeto.metodoPublico1); // mostra ele
console.log("metodoPublico1", meuObjeto.metodoPublico1()); // executa metodo publico
console.log("metodoPublico2", meuObjeto.metodoPublico2()); // executa metodo publico
console.log("metodoPublico3", meuObjeto.metodoPublico3()); // executa metodo publico

console.log("metodoPrivado1", meuObjeto.metodoPrivado1); // nao tem acesso
console.log("metodoPrivado2", meuObjeto.metodoPrivado2); // nao tem acesso
console.log("metodoPrivado3", meuObjeto.metodoPrivado3); // nao tem acesso


console.log("variavelPublica1", meuObjeto.variavelPublica1); // Acessa diretamente
console.log("variavelPublica2", meuObjeto.variavelPublica2); // Acessa diretamente

console.log("setVariavelPrivada1 = XPTO");
meuObjeto.setVariavelPrivada1("XPTO");
console.log("variavelPrivada1", meuObjeto.variavelPrivada1); // tenta acessar diretamente, nao consegue
console.log("getVariavelPrivada1", meuObjeto.getVariavelPrivada1()); // usa getter
```