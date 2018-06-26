# Classes

Classes em JavaScript são introduzidas no ECMAScript 6 e são simplificações da linguagem para as heranças baseadas nos protótipos. A sintaxe para classes não introduz um novo modelo de herança de orientação a objetos em JavaScript. Classes em JavaScript provêm uma maneira mais simples e clara de criar objetos e lidar com herança.

```javascript
class Poligono {
  constructor(altura, largura) {
    this.nome = 'Polígono';
    this.altura = altura;
    this.largura = largura;
  }
}

class Quadrado extends Poligono {
  constructor(altura) {
    super(altura, altura);
    this.nome = 'Quadrado';
  }
}
```