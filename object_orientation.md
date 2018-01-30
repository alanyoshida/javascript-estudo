# Object Orientation

```javascript
/* ################################################################################ */
// BASIC OBJECT CREATION

// This is the base object that will be used as the model for creating other objects
var answer = {
    get: function(){
        return this.val;
    },
    val: 42
};

// Creating other objs based on answer object.
var firmAnswer = Object.create(answer);

// overwriting get function of the object
firmAnswer.get = function(){
    /*
    calling the function of the parent object but
    the call function will set the 'this' keyword for the current object
    so when the function get uses the 'this' keyword it will be of the
    current object, not the parent.
    */
    return answer.get.call(this) + "!!";
};

firmAnswer.val = 3.14159;

var result = firmAnswer.get();
console.log( 'RESULT IS: ', result );

/* ################################################################################ */
// BASIC OBJECT CREATION WITH THE NEW KEYWORD

// Creates the constructor function
function Answer(value){
    this._val = value;
}

Answer.prototype.get = function(){
    return this._val;
}

// Creating the Object based on the constructor
var lifeAnswer = new Answer(42); // the new keyword looks for the constructor function to be called
var result = lifeAnswer.get();
console.log( result );

// Some debugging to better understand

typeof Answer; // function
typeof Answer.prototype; // Object

Answer.prototype;
/*
Object {}
    constructor: Answer(value)
    get: function()
    __proto__: Object
*/

/* ################################################################################ */
// POLYMORFISM

// This is the base object that will be used as the model for creating other objects
var answer = {
    get: function(){
        return this.val;
    },
    val: 42
};

// Creating other objs based on answer object.
var firmAnswer = Object.create(answer);

// overwriting get function of the object
firmAnswer.get = function(){
    /*
    calling the function of the parent object but
    the call function will set the 'this' keyword for the current object
    so when the function get uses the 'this' keyword it will be of the
    current object, not the parent.
    */
    return answer.get.call(this) + "!!";
};

firmAnswer.val = 3.14159;

var result = firmAnswer.get();
console.log( 'RESULT IS: ', result );

/* ################################################################################ */
// SUBCLASS and INHERITANCE using the new keyword

// Creates the constructor function
function Answer(value){
    this._val = value;
}

Answer.prototype.get = function(){
    return this._val;
}

// Creating the Object based on the constructor
var lifeAnswer = new Answer(42); // the new keyword looks for the constructor function to be called
var result = lifeAnswer.get();
// console.log('lifeAnswer Result: ', result );

/* Creating the subclass */
function FirmAnswer(value){
    // This calls the parent constructor and pass the parameters as well
    Answer.call(this, value);
}

/*
Answer.prototype is the object with constructor that is the function Answer, and the get function
Object.create() creates a new object based on the Answer.prototype
FirmAnswer.prototype receives this new object that is the Answer,
so it sets the inheritance, with means if something is not
found in FirmAnswer it looks for the prototype to find the called function.
*/
FirmAnswer.prototype = Object.create(Answer.prototype);

/*
This sets the FirmAnswer to be the constructor, not its parent constructor
with means that it ovewrites the parent constructor to be
the actual declared function */
FirmAnswer.prototype.constructor = FirmAnswer;

/* This ovewrites the get function (polymorfism) */
FirmAnswer.prototype.get = function(){
    return Answer.prototype.get.call(this) + "!!";
}

var luckyAnswer = new FirmAnswer(7);
luckyAnswer.get();


/* ################################################################################ */
// Subclass without the new keyword

// Creates the constructor function
var Answer = {
    constructor: function(value){
        this._val = value;
    },
    get: function(){
        return this._val;
    }
};

// Creating the Object based on the other obj ( Inheritance)
var lifeAnswer = Object.create(Answer);
lifeAnswer.constructor(42);
var result = lifeAnswer.get();
console.log('lifeAnswer Result: ', result );

/* Creating the obj of subclass */
var FirmAnswer = Object.create(Answer);

// Overwriting the function get of parent
FirmAnswer.get = function(){
    return Answer.get.call(this) + "!!";
}

// Creating a Object from the "subclass"
var luckyAnswer = Object.create(FirmAnswer)
luckyAnswer.constructor(7);
var result2 = luckyAnswer.get();
console.log('LuckyAnswer: ', result2);

```
