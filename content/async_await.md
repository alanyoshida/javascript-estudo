# Async await

```javascript

function resolverDepoisDe2Segundos(x) {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve(x);
    }, 2000);
  });
}

async function adicionar1(x) {
  var a = resolverDepoisDe2Segundos(20);
  var b = resolverDepoisDe2Segundos(30);
  return x + await a + await b;
}

adicionar1(10).then(v => {
  console.log(v);  // printa 60 depois de 2 segundos.
});

async function adicionar2(x) {
  var a = await resolverDepoisDe2Segundos(20);
  var b = await resolverDepoisDe2Segundos(30);
  return x + a + b;
}

adicionar2(10).then(v => {
  console.log(v);  // printa 60 depois de 4 segundos.
});

```
