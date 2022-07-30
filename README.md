# js-practices
Just an MD file to put one of the best js good practices that I have realised as Frontend Developer

 ## Declare Variables Outside of the For Statement

```other
for (attribute in array) {
	 // 😔
	 const container = document.getElementById('container');
	 ...
}
```

   The code above make the engine work any harder than it must. We traverse the DOM to find the "container" element each time—highly inefficient!

 ## Use Template Literals

```other
const person = 'David';
const age = 28;

// 😔
const message = person + ' has ' + age ' years old';

// Better 😎
const message = `${person} has ${age} years old`;
```

   Template literals are created using the backtick character (```), and they offer many advantages. This reduces the chances of any typing-related errors and helps us write cleaner code.

 ## Consider Using `let` and `const`

```other
// Bad 😔
var message = 'Hello World';

// Use let or const instead 😎
const message = 'Hello World';
```

   The `let` keyword allows us to create variables that can change, and `const` keyword allows us to create variables whose value cannot be reassigned. Keep in mind that the const keyword only prevents reassignment, it does not make the variable immutable.

 ## Use `[]` instead of `new Array()`

```other
// 😔
const a = new Array();
a[0] = 'Hello';

//Better 😎
const a = ['Hello'];
```

 ## Use the Spread Operator

```other
const array = ['Hello, 'World', 'Team'];
const newArray = ['Cuba', ...array];
```

   This JavaScript functionality is for array and objects also.

 ## Use ES6 Destructuring for variable declarations if needed

```other
const obj = {
	kind: 'Hapiness',
	hobby: 'Music',
	place: 'Europe'
	teamName: 'Havana Club Rum 😂'
};

// Bad 😔
const kind = obj.kind;
const hobby = obj.hobby;
const place = obj.place;


// Better (with destructuring) 😎
const {kind, hobby, place} = obj;
```

   Destructuring simply implies breaking down a complex structure into simpler parts.

 ## Iterators, for of “loop”

```other
const companies = ["Microsoft", "Google", "Apple"];
const length = companies.length;
// 😔 If not necesarry strict this iterator use "for of" instead
for(let i = 0; i < length; i++) {
    console.log(companies[i]);
}

//Better 😎
for(company of companies) {
	console.log(company);
}
```

   With a  loop, we don't have to keep track of the total length of the array or the current index. This can reduce code complexity when creating nested loops.for...of. By the way, avoid nested loops as much as possible. Even, if it’s neccesary use classic “for” iterator, the length of array would be best declare outside loop, just as wroten.

 ## Async await use for Promises

```other
function showMessage() {
    return new Promise((resolve) => setTimeout(() => resolve("Hello World!"), 2000));
 }

// Classic call
showMessage.then(data=>{
	console.log(data);
})

//Better call with await 😎
console.log(await showMessage());
```

   You can use the  keyword to create asynchronous functions, which always return a promise either explicitly or implicitly. Asynchronous functions that you create can take advantage of the  keyword by stopping execution until the resolution of returned promises.

 ## Use Arrow Functions

```other
const nums = [1,2,3,4,5,6,7,8];

// 😔
const tempNums = nums.filter(function(n) { 
	 ... 
})

// Better 😎
const tempNums = nums.filter(n => ...)
```

   Arrow functions make the functional elements of JavaScript more appealing to the eye and easier to write. Also they do not define a scope, instead being within the parent scope. This prevents many of the issues that can occur when using the keyword.

 ## Run Promises in Parallel

```other
// 🥳
const urls = ["https://google.com", "https://wikipedia.org"];
const inf = await Promise.all(urls.map(async url => await fetch(url)));
```

   Run promises in parallel can make your app much faster and more responsive. If your tasks don't rely on the results from one another, simply wrap them in and run them with “Promise.all"

   By the way, Rxjs library is also a very important technology to use which manage async code. Observables are not native part of javascript but it’s top used.

 ## Use Splice to Remove Items From an Array

```other
const items = ["ice cream","fruits","milk"];
items.splice(2,1);
```

 ## Use Function expressions instead of Function Declarations

```other
// 😔
const myFn = function() {...}

// 😎
function myFn() {...}
```

   Unless you want to take advantage of Function behavior and properties, prefer function expressions. Function declarations are hoisted and although it can be useful sometimes, avoid them as they introduce weird behavior to the code and it is not always obvious what's happening.

 ## Prefer Pure Functions

```other
// 😔
function myFn(array) {
	for (const index in array){
		array[index] *= 2;
	}
	return array;
}

// 😎
function myFn(array) {
 return array.map(n => n * 2);
}
```

   Ensure your functions are not changing data they are called with or data in the scope where they are created.

 ## Simplify with optional chaining

```other
// 😔
if(data && data.someThing && data.someThing.name = 'Hello World') {...} 

// 😎
if(data?.someThing?.name = 'Hello World') {...}
```

   Get rid of those nested checks and use the “?” operator.

 ### Use `===` Instead of `==`

   `10 === 10 // true`

It is considered best practice to always use strict equality when comparing.

16. ## 🧐 Always “try…catch” JSON methods

Don't trust things passed to JSON methods “.stringify” and “.parse”. Try to catch them to make sure they don't fail and break your code.

17. ## Watch out for “undefined” and “null” with the “??” operator

   The nullish coalescing operator makes sure that null and undefined values are not picked and it is perfect for cases where you want to ensure that there is a value or fallback to a default value.

- ## Others important
   1. Don't initialize variables with “undefined”.
   2. Always initialize your declarations.
   3. Organize your declarations.
      1. Declarations on top.
      2. Always const variables first.
      3. For key values map on json files, if possible organize the keys alphabetically.
   4. Avoid unnecessary comments.
   5. Use TypeScript as much as possible.
   6. Functions and methods should do one thing only (Single Responsability Principle).
   7. Use Facade Pattern when working with inherit (better implementation with TS).
   8. Always have a default case for switch statements.
   9. Avoid the “new” keyword because they can slow compilers down.
   10. Keep ternaries simple.
   11. Avoid nesting or chaining loops.
   12. Add semicolons, always!
   13. Never trust data you don't create.
   14. Avoid repeating yourself with utilities (DRY).
   15. …


