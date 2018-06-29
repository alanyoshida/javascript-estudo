# Export

O export é usado para exportar funções, objetos ou valores primitivos de um arquivo (ou módulo).

Por enquanto esse recurso não está implementado nativamente. 

Ele é implementado em vários transpiladores, tais como Traceur Compiler, Babel ou Rollup.

```javascript
export { name1, name2, …, nameN };
export { variable1 as name1, variable2 as name2, …, nameN };
export let name1, name2, …, nameN; // also var
export let name1 = …, name2 = …, …, nameN; // also var, const

export default expression;
export default function (…) { … } // also class, function*
export default function name1(…) { … } // also class, function*
export { name1 as default, … };

export * from …;
export { name1, name2, …, nameN } from …;
export { import1 as name1, import2 as name2, …, nameN } from …;
```

# Import

O import é usado para importar funções, objetos ou valores primitivos de um arquivo (ou módulo).

Por enquanto esse recurso não está implementado nativamente.

Ele é implementado em vários transpiladores, tais como Traceur Compiler, Babel ou Rollup.

```javascript
import membroPadrao from "nome-do-modulo";
import * as nome from "nome-do-modulo";
import { membro } from "nome-do-modulo";
import { membro as apelido } from "nome-do-modulo";
import { membro1 , membro2 } from "nome-do-modulo";
import { membro1 , membro2 as apelido2 , [...] } from "nome-do-modulo";
import membroPadrao, { member [ , [...] ] } from "nome-do-modulo";
import membroPadrao, * as nome from "nome-do-modulo";
import "nome-do-modulo";
```