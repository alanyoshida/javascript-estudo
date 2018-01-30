# Generators

```javascript
// USING GENERATOR
run( function *(){
	const uri = 'http://jsonplaceholder.typicode.com/posts/1';
	const response = yield fetch(uri);
	const post = yield response.json();
	const title = post.title;
	console.log('Title: ', title);
});

THE GENERATOR THAT RESOLVES THE RUN ABOVE
function run(generator) {
	const iterator = generator();
	const iteration = iterator.next();
	const promise = iteration.value;
	promise.then( x => {
		const anotherIterator = iterator.next(x);
		const anotherPromise = anotherIterator.value;
		anotherPromise.then( y => iterator.next(y));
	});
}

// GENERATOR WITH RECURSION
function run(generator) {
	const iterator = generator();
	function iterate(iteration){
		if(iteration.done) return iteration.value;
		const promise = iteration.value;
		return promise.then( x => iterate(iterator.next(x)));
	}
	return iterate(iterator.next());
}
```
