#### Let and Var
1. both let and var can be used in globle scope, however var can be easily redifined and let cannot;<br />
###### Var
```
'use strict';
var temp = "this is a temp variable";
var temp = "this is a second temp variable"; //replaced easily
```
###### Let
```
'use strict';
let temp = "this is a temp variable";
let temp = "this is a second temp variable" //SyntaxError: temp is already declared
```
2. Let won't get assign to Window object
```
console.log(window.varVariable); //this is a var variable
console.log(window.letVariable); //undefined
```
3. <em><strong>Let</strong> is block scoped</em>: if it is defined inside the scope, you won't be able to see access it outside

 <div style="background-color:rgba(0, 0, 0, 0.0470588); text-align:center; vertical-align: middle; padding:40px 0; margin-top:30px">
let gives you the privilege to declare variables that are limited in scope to the block, statement of expression unlike var.<br/>
var is rather a keyword which defines a variable globally regardless of block scope.
 </div>
