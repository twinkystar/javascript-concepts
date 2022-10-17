# Shadowing in JS

```js
var a =10; //in global memory
let b =10; //in other (script) memory
{ //block scope
	var a =20; //shadowing - value of a gets shadowed (in block memory)
  let b =20; //(in block memory)
console.log(a,b); //20,20
}
console.log(a,b); //20,10 (var globally scoped, let block)

function yo() { //function scope
	var a =30;  //new a and b (in function memory)
  let b =30;(in function memory)
  console.log(a,b); //30,30
}
console.log(a,b); //20,10 (var globally scoped, let block)
```

## Illegal shadowing: (can't make const/let to var)

```js
let a=10;
{ var a=20;} //error
```

But, Valid shadowing
```js
let a=10;
{ let a=20;} 
 
And 
Var a=10;
{ let a=20;} 
```
