# Currying

```javascript
var filmes = [
{ name: 'Matrix', genero: 'acao'}
,{ name: 'Mad Max', genero: 'acao'}
,{ name: 'Interestelar', genero: 'ficcao cientifica'}
,{ name: 'A origem', genero: 'ficcao cientifica'}
,{ name: 'Seven', genero: 'policial'}
];

var hasGenero = function(genero){
  return function(obj){
    return obj.genero === genero;
  }
};

var FilmesAcao = filmes.filter(hasGenero('acao'));

console.log('Filmes de acao: \n', FilmesAcao);

console.log('\n');

var FilmesFiccao = filmes.filter(hasGenero('ficcao cientifica'));

console.log('Filmes de ficcao cientifica: \n',FilmesFiccao);
```
