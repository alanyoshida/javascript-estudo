# Partials

```javascript
// Where the magic happens
function partialApplication( f, a ) {
    return function( b ) {
        return f( a, b )
    }
}

function greet( title, name ) {
    return "Greetings " + title + " " + name
}

// Here you pass the function to be executed, and the first parameter
var greetSer = partialApplication( greet, "Ser" )

// Here you pass the second parameter
var character1 = greetSer( "Barristan" ) // Greetings Ser Barristan
console.info(character1);

var character2 = greetSer( "Davos" ) // Greetings Ser Davos
console.info(character2);


// Other ways, using fixed parameters as left or right

function leftApply( f, a ) {
    return function( b ) {
        return f( a, b )
    }
}

function rightApply( f, b ) {
    return function( a ) {
        return f( a, b )
    }
}
```

## Other Examples

```javascript
// original function
function filterBy( key, val, arr ) {
    return arr.filter( el => el[ key ] === val )
}

// original usage
filterBy( "category", "food", products )
filterBy( "weight", "1kg", products )

// left-most parameter is applied
const filterByCategory = leftApply( filterBy, "category" )
const filterByWeight = leftApply( filterBy, "weight" )

filterByCategory( "food", products )
filterByCategory( "electronics", products )
filterByWeight( "1kg", products )

// two parameters are applied
const filterFood = leftApply( filterBy, "category", "food" )

filterFood( products )

// applying the function against the same collection always
const filterProducts = rightApply( filterBy, products )

filterProducts( "category", "food" )
filterProducts( "weight", "1kg" )

// composing left and right apply
const filterProductsByCategory = leftApply( rightApply( filterBy, products ), "category" )

filterProductsByCategory( "food" )
filterProductsByCategory( "electronics" )
```
