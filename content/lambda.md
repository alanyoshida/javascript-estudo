# Lambda

```javascript
/* ES5 */
var adderEs5 = function(x){
  return function(y){
    return x+y;
  };
}

var result1 = adderEs5(5)(5);
console.log(result1);
// 10

/* ES6 */
var adderEs6 = x => y => x+y;

var result2 = adderEs6(6)(6);
console.log(result2);
 // 12
 ```
