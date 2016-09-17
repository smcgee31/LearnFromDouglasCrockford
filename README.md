# Learning from Douglas Crockford - YouTube video series called "Crock on JS"

skipped to video 3 to start... first two videos are about the early years and history of the language.

## Video 3 : Function the Ultimate
#### VAR Statement

var gets split into two `parts` and hoisted...
Part 1:
```js
var myVar = 0,
	myOtherVar;
```
Expands into:
```js
var myVar = undefined,
	myOtherVar = undefined;
```
both of which are hoisted to the top of the function.
Then at the point of the function where the original var was is now a assignment statement...
```js
myVar = 0;
```
#### Scope
In JS blocks do not have scope. Only functions have scope.
Variables defined inside a function are not visible outside the function.
```js
function assure_positive(matrix, n) {
	for (var i = 0; i < n; i++) {
		var row = matrix[i];
		for (var i = 0; i < row.length; i++) {
			if (fow[i] < 0) {
				throw new Error('blahblah');
			}
		}
	}
}
```
The function written above would silently fail because the function would run forever. The programmer thinks they've written two 'i' variables but in fact there's only ONE 'i' variable and so the inner loop keeps resetting the 'i' value so the outer loop will never finish.

So it is recommended to declare all variables at the top of the function and declare all functions before you call them.

#### Return Statement
```js
return `expression`;
```
OR
```js
return;
```
If there is no *expression*, then the return value is undefined.
**Except** for constructors, whose default return value is `this`.
Note: no line break after a return because semicolon insertion would turn the return into an undefined return statement.

#### Arguments
There are two pseudo parameters that every function can receive...
`arguments`
`this`

