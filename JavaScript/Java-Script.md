# 📔 ES5

## 📘 Developer Resposibilty

Write good code so everyone can read and understand easily

## Conceptual Aside 
1. **syntax parsers**: A syntax parser is a part of java script engine its reads your code character by character and tells what your code does and 
    checks if the grammar is correct or not. it translates your code to machine readable code 

                       _example_=> parsing-->grammar checking-->language

````javascript
//your code

function hello(){
var a = 'hello';
}

computer instructions

function
   variable
````




2.**Lexical Environment**:Means exists in programing languages in which where you write something is important 
                                                   or 
                         physical code where you write the code in the programing 
                    
3.**Execution Context** : There are lots of Lexical Environment which  one is running is managed via  execution Context. Its can contian
    thing beyond what your written in your code         
    Whenever you run a code in execution context its create a **Global object, this** by the javascript engine
    IN javascript  **window == this**
in execution phase there are three phase **Global object,this,outer enviroment,Runs your code**
````javascript
example 

var a= 'aman';
function b (){
} 
// so in this example  the variable is global and function is also global execution context  if the function call then is create its on execution context
````
    
  ## 📘 Name/Value Pairs and Objects
   * The name may be defined more than once , but only can have one vale in any given context
   * That value may be more name/value pair 
   * **Object** : A Collection of name values pairs. The simplest definatian when talking about java script.

       ![download](https://github.com/amandavid0032/aman/assets/86879390/cec80157-7810-4f3e-9141-46e923b20858)
   
  **Name/value**
   ![name-value](https://github.com/amandavid0032/aman/assets/86879390/93cce369-a8ce-4fc0-b84c-9098e0e5994c)

````javascript
   **Example==>** 

   Address:{
     street :'Main',                           
     Number : 100                              
       Appartment:     
        {
          Floor : 3,
          Number: 301
         }
     }

  // street is the name and main is value, number is the name and 100 is the value.
````
## 📘Creation & Hoisting

Javascript Execution Context has two phase <br/>
1. **Creation Phase**: Set up memory for variables and functions, also set placeholder for variables called **undefined**.
2. **Execution Phase**: means assignee values to variables but not for functions.

In javascript __variables and functions__ are all hoisted to the top of the scope in which they are declared. The scope is usually either global scope or a function scope.
 
 * varibles are always __partially hoisted__ and set to __undefined__.
 * functions are always __fully hoisted__.


so during the creation phase javascript engine moves your variables and function decelerations of the top their respective scope
javascript
````javascript
//example of variable in this variable is partial hosted

console.log(number1);
var number1 = 10;
 
// javascript is doing this process in background
var number1;

console.log(number1);

number1 = 10;

// Function 
function test(){
 console.log(a);
 console.log(b);
var a = 10;
var b = 20;
}
test();        // output undefined undefined
````

````javascript
// Function in background running 
function test(){
var a = 10; 
var b = 20;
console.log(a);
 console.log(b);   
}
test();    //output undefined  but in function its set the creation and execution and this process is called hosted.


`````


## 📘Undefined vs Not Defined
* **undefined** : is special value in java script, it will take memory space and in undefined variable value is not define or set.

```javascript
// undefined : means value is not set
var number1;
console.log(number1);
number1 = 10;
```
```javascript
// Not defined : means does not exist or not defined or variable is not exist
console.log(number1);
```
## 📘 The Global Environment and The Global Object
* when ever code is run in javascript it's run inside an execution context. Meaning a wrapper that the javascript engine wrap that up, that code that you've written in **global execution**.

![gloabl-environment](https://github.com/amandavid0032/aman/assets/86879390/38ee0b7e-c252-4938-86e4-38ce0aec641d)
* In Browser its create a this and this == window 

```javascript
var a = 10;
function b() {
    console.log('hello world');
}
a         // 10
window.a  // 10
this.a    // 10   

b();        // hello wolrd
window.b(); 
this.window.b();
```
_code explantion_ ==> b is a function and show the output `hello world` , then window.b call window is object show  `hello world` , this.window.b show `hello world` 

## 📘 The Execution Context : Code Execution (Your Code)
Code Execute line by line

```javascript
test();

console.log(a);             // undefined

var a = 'Hello world';

console.log(a);

function test() {
    console.log('Hello world');
}
```
---
## 📘Single Threaded, Synchronouse Execution
 * **Single Threaded :** one command at a time. Under the hood of the browser, maybe not.
                         doing one job at a one time 
 * **Synchronouse :** one at a time.
## Function Invocation and The Execution Stack
* **Invocation** : Running a function. in javascript, by using **parenthesis()**
* when ever a function get invoke it will create new **Execuion Context** for it for example **a() && b()** creating its own execution context.
![function-invocation-and-the-execution-stack (2)](https://github.com/amandavid0032/aman/assets/86879390/15996a79-dec0-416b-a272-5149170abff2)

---
## 📘 Functions, Context and Variable Environments
* **Variable Environments :** Where the variables live. and how they related to each other in memory.

![function-invocation-and-the-execution-stack (3)](https://github.com/amandavid0032/aman/assets/86879390/eccf46ec-cae1-45b7-a0d3-940276d38fe3)

* Value of variables also depend upon **scope**. in below example the value of **myVar** depends upon scope.
```javascript
function b(){
    var myVar;
    console.log(myvar);
}
function a() {
    var myVar = 2;
    console.log(myVar);
    b();
}

var myVar = 1;
console.log(myVar);
a();
console.log(myVar);
```
---
## The Scope Chain

* **Scope :** where a varaiable is available in your code. and if it's truly the same variable or a new copy

```javascript
// function 'b' is sit lexically sits on top of global environment, in the other words it's not inside function 'a', it is sitting at the global level

function b() {
    console.log(myVar);
}

function a() {
    var myVar = 2;
    b(); 
}

var myVar = 1;
a();

```
![scope-chain (1)](https://github.com/amandavid0032/aman/assets/86879390/011ffb70-e42c-4dbe-8b78-fd851b9e1011)


```javascript
// function 'b' is sit lexically inside the function 'a'

function a() {
    function b() {
        console.log(myVar);
    }

    var myVar = 2;
    b(); 
}

var myVar = 1;
a();
---
![scope-chain-another-example](https://github.com/amandavid0032/aman/assets/86879390/af29a467-b22d-4134-b8ed-758fcd0b0eac)

```
## 📘 What about Asynchronouse Callbacks
* **Asynchronouse :** more than one at a time. Doing a multiple job at one time.

## 📘 Types and Javascript
* **Dynamic Typing :** : you don't tell the engine what type of data a variable holds, it figures it out while your coding is running. Variables can hold different types of values beacuse it's all figured out during execution.

``` javascript
// Static  Typing

bool isNew = 'hello'; // an error

// Dynamic Typing 
var isNew = true;   // no error
isNew = 'yup!';
isNew = 1;
```
---
## 📘 Primitive types
* **Primitive type :** A type of data that represents a single value. That is, not an object.

1. **undefined :** undefined represents lack of existance (you should'nt set a varaible to this)
2. **Null :** null represents lack of existance (you can set a variable to this)
3. **Boolean** : true or false
4. **Number :** Floating point number (there's always some decimals). Unlike other programming languages, there's only one 'number' type ... and it can make math weird. 
5. **String :** a sequence of character (both '' and "" can be used)
6. **Symbol :** used in ES6   
**Non-primitive:**

1.object
2. Array
---

## 📘 Operator Precedence and Associativity
* **Operator Precedence :** which operator function gets called first. Functions are called in order of precedence (HIGHER precendence wins). Example : BDMAS
```javascript
var a = 3 + 4 * 5;
console.log(a); //23 
```
* **Associativity :** What order operator functions get called in: LEFT-TO-RIGHT or RIGHT-TO-LEFT. when functions have the *same* precedence. Example : 1+2+3/3/4
---
## 📘 Coercion
* **Coercion :** Converting a value from one type to another. This happens quite in javascript beacuse it's dynamically typed. This happens quite often in javascript beacuse it's dynamically typed. 

```javascript
var a = 1 + '2';
console.log(a);     //12
```
Explation--> in this 1 is number but second parameter is string to javascript add t string with one so the output is 12.

```javascript
var a = A + + b;
console.log(a);     //ANaN
```
Explation--> IN this example A is the string but thee is 2 + + second (+) converts into number its pass the string into numeric value but string can't pass into number so its evaluates  to NaN(not a number ) so its return the NaN so the output is ANaN 

```
## 📘 Comparsion

```javascript
var a = 3 < 2 < 1 ;
console.log(a);

var a = 1 < 2 < 3
console.log(a);

Number(undefined) // NaN
Number(null)    // 0
Number(false)   // 0
Number(true)    // 1

1 == '1'    // true
1 === '1'   // false
```
````
var a =10;
var b= '10';
if (a==b){
console.log('They are equal!');
}
else{
console.log('Nope, not equal.'); 
}                  // output They are equal
````
In this example its check only value not a data type nd it is not a good.  **Equalityxx **

````
var a =10;
var b= '10';
if (a==b){
console.log('They are equal!');
}
else{
console.log('Nope, not equal.');
}  // output nope not equal
````
In this its checks the data type also  **Strict Equality**
````
## 📘 Existence and Booleans

```javascript
Boolean(undefined)      // false
Boolean(null)           // false
Boolean("")             // false
Boolean(0)              // false

// Example 1
var a;
if(a) {                 // will not execute
    console.log('Something is there');
}

// Example 2
var a;
a = 0;

if(a || a === 0) {      // will execute 
//  because === has higher order precedence than or operator    
 console.log('Something is there');
}
````
## 📘 Default Value
* operators are functions example || (OR Operator is a function) or **return value** operators return true value
```javascript
undefined || 'hi'       // hi
'hi' || 'hello'         // hello
null || 'hi'            // hi
0 || 'hi'               // hi
````
````javascript
// Example 1
function greet(name) {
    // '||' operator has high precendece then '='
    name = name || '<Your name here>';
    console.log('Hello' + name);
}
greet();
````

## 📘 Objects and Dot
![object-dot](https://github.com/amandavid0032/aman/assets/86879390/4d71523f-a3d3-4fc8-89c9-e67caaeeb9fa)
0*001
0*002
This are address of object of property  in memory

```javascript
var person = new Object();

// [] is a operator

person['firstname'] = "Tony";
person['lastname'] = "Alicea";

var firstNameProprty = "firstname";
console.log(person);
console.log(person[firstNameProprty]);

// . is a operator
console.log(person.firstname);

person.address = new Object();

// . has left-to-right associativity
person.address.street = "51 d street no 3 ranjit nagar near seona chowk patiala punjab";

console.log(person.address.street);
console.log(person['address']['street']);
```
---
---
## 📘Objects and Object Literals

```javascript
// comparing current example with abov example the object literials are easy to write and easy to read
var person = { 
    firstname : 'Tony',
    lastname : 'Alicea',
    addres : {
        street : "51 d street no 3 ranjit nagar near seona chowk patiala punjab"
    } 
};
console.log(person);
````
````javascript
// Example of creating Object on Fly

function greet(person) {
    console.log('Hi' + person.firstname);
}

var Tony = { 
    firstname : 'Tony',
    lastname : 'Alicea',
    addres : {
        street : "51 d street no 3 ranjit nagar near seona chowk patiala punjab"
    } 
};

greet(Tony);

// creating object on fly
greet({
    firstname : 'Mary',
    lastname : 'Doe'
});

```
---
## 📘 Namespace : 
* **Namespace :** a container for variables and functions. Typically to keep variables functions with the same name separate.

```javascript
var greet = 'Hello!';
var greet = 'Hola!';
console.log(greet);

// namespacing helping to resolve the issue of namespace collisions (means same name variables)
var english = {};
var spanish = {};

english.greet = 'Hello!';
spanish.greet = 'Hola!';

console.log(english.greet);
console.log(spanish.greet);
```
---
## 📘 Namespace : 
* **Namespace :** a container for variables and functions. Typically to keep variables functions with the same name separate.

```javascript
var greet = 'Hello!';
var greet = 'Hola!';
console.log(greet); // its show the output hola 

// namespacing helping to resolve the issue of namespace collisions (means same name variables)
var english = {};
var spanish = {};

english.greet = 'Hello!';
spanish.greet = 'Hola!';

console.log(english.greet);
console.log(spanish.greet);
```
---
## 📘 JSON and Object Literals

* **JSON :** javascript object notation. **_read later not done this topic know _**

```javascript

var objectLiteral = {
    firstname : 'Mary',
    isAprogrammer : true
}

console.log(objectLiteral)

// json format
{
    "firstname" : 'Mary',
    "isAprogrammer" : true
}
```
1. **JSON,stringify(ObjectLiteral) :** it will convert JS Object into JSON String.
2. **JSON.parse(string) :** it will convert JSON string into JS Object.

## 📘 Functions are Object
* **First Class Functions :** Everything you can do with other types you can do with functions. Assign them to variables, pass them around, create them on the fly.
![funtions-are-object](https://github.com/amandavid0032/aman/assets/86879390/b053d2d3-e7e2-487a-ba6f-aba32fc425d7)

```javascript

function greet() {
    console.log('hi');
}

// adding property to function
greet.language = 'english';

// print name property of function
console.log(greet)

// printing property which we are attaching to it
console.log(greet.language)
```
![example-functions-are-object](https://github.com/amandavid0032/aman/assets/86879390/493b59a6-dc84-4398-84b6-38a56e8beffc)
## 📘 Function Statements and Function Expressions
* **Epression :** A unit of code that results in a value. It does n't have to save to a variable.

```javascript
// mean concept is that what ever the variable returnning a value is called expression like number, object etc 
var a = 3
var b = 1 + 2;
var c = {greeting : 'hi'}

// here (a === 3) is expression beacuse it return some value && if is just simply statement it not returnning any value.

// so statment just does work and an expression results in a value
if (a == 3) {

}
```
* **Function Statement :** the statement which does not return any thing, it just statement.

```javascript
function greet() {
    console.log('hi');
}
```
* **Function Expression :** the statement which retun any thing.
  
```javascript
// beacuse here function is considered as object and creating on fly && it returns an object heance its a value 
var anonymousGreet = function () {
    console.log('hi');
}
anonymousGreet();


```
![function-epressions-invoke](https://github.com/amandavid0032/aman/assets/86879390/f953c587-3785-484b-ac32-e7fb16c19b4a)
⚠️ **Note** : Function Expresions are not hoisted

```javascript
// Functions expressions considered as variable and According to Hoisting variables are set to undefined

anonymousGreet();   // error : undfined is not a function

var anonymousGreet = function () {
    console.log('hi');
}
```
---
## 📘 Pass By Value Vs By Reference

* **Mutate :** To change something.
* **Immutable :** means it can't be changed.
![pass-by-value](https://github.com/amandavid0032/aman/assets/86879390/8de5f287-78be-4e13-8f24-95695c439a19)

* **Pass by value :** Simply means we copy the value and we create that value some where else in memory all **primitves types** are *Pass by refernce* examples. number, boolean, string etc or its make a copy of data which take memory and its slow 
```javascript
var a = 10;
var b = a;
var a = 11;

console.log(a) // 11
console.log(b) // 10
```
![pass-by-refrence](https://github.com/amandavid0032/aman/assets/86879390/6ebd87dc-bf4e-43b6-afe2-ff6eb3e9d762)
*  __Pass by Reference__ : Objects in javacsript are stored in memory and are passed by reference. This means that we don't copy the value are did with primitive types. All **Objects types** are *Pass by reference* examples. array, funtions and objects

```javascript
let obj1 = { name: "Deepu", password: "123" };
let obj2 = obj1;
obj2.password = '456';

// { name: "Deepu", password: "456" };
console.log(obj1);

// { name: "Deepu", password: "456" };
console.log(obj2);
```

* **By Reference (even as Parameter)**

```javascript
function changeGreeting(obj) {
    obj.name = 'dp'; // mutate
}

changeGreeting(obj2);

// { name: "dp", password: "456" };
console.log(obj1);

// { name: "dp", password: "456" };
console.log(obj2);

// equals operators sets up a new memrory space (new Address)
obj1 = {name : 'Noni', password : '123'};

console.log(obj1)
// {name : 'Noni', password : '123'}

console.log(obj2)
// { name: "dp", password: "456" };
```
## 📘 Objects, Functions and This
The __this__ keyword is actually pretty straightforward to understand __what is does is it refers to whatever object it is directly inside (property) of.__

* On Global Level : __this === window object__
* On Object Level : __this === current Object__ 

```javascript
// globale execution context
console.log(this);       // window object

// Function A Execution context and getting own this kwyword but it pointing to window object (same memory location)
function a() {
    console.log(this);   // window object  
    this.newVariable = 'hello';
}
a();
// Function B Execution context and getting own this kwyword but it pointing to window object (same memory location)
var b = function () {
    console.log(this);   // window object
}
console.log(newVariable);   // hello
b();
````
````javascript
//Problem
var c={
    name: 'The c is object',
    log:function(){
        this.name='updte c  object by aman';
        console.log('this');
        var setname=function(newname){
            this.name=newname;
        }
        setname('update again! the c object');
        console.log(this);
    }
}
c.log();
````
````javascript
//solution

var c={
    name: 'The c is object',
    log:function(){
        var self=this;
        self.name='updte c  object by aman';
        console.log('self');
        var setname=function(newname){
            self.name=newname;
        }
        setname('update again! the c object');
        console.log(self);
    }
}
c.log();
````

```javascript
let obj = {
    firstName: 'Deepu',
    lastName: 'Singh',
    // here this is attached to the current object by javascript engine
    log: function(){
        this.name = 'Deepinder',
        console.log(this);
    }, 
    getFullName: function () {
        return this.firstName + ' ' + this.lastName;
    }
}

obj.firstName // Deepu
obj.getFullName() // Deepu Bhasin
```
### 📑Self and Scope (with This)
Problem 

```javascript
var firstName = "Deepinder";

let obj = {
    firstName: "Deepu",
    getFullName: function () {
        console.log('First Name', this.firstName);
        
        function test() {
        // here it 'this' will refere to the window object
            console.log('First Name', this.firstName);
        }
        test();
    }
}

obj.getFullName();    
```

Solution 

1. By Passing reference of current object

```javascript
var firstName = "Deepinder";

let obj = {
    firstName: "Deepu",
    getFullName: function () {
        console.log('First Name', this.firstName);
        
        // passing reference 
        var self = this;
        
        function test() {
            console.log('First Name', self.firstName);
        }
        test();
    }
}

obj.getFullName();    
```
2. By binding 'this' with bind function

```javascript
var firstName = "Deepinder";

let obj = {
    firstName: "Deepu",
    getFullName: function () {
        console.log('First Name', this.firstName);
        
        function test() {
            console.log('First Name', this.firstName);
        }
        test.bind(this)();
    }
}

obj.getFullName();    
```

1. By using Arrow function

```javascript
var firstName = "Deepinder";

let obj = {
    firstName: "Deepu",
    getFullName : () => {
        console.log('First Name', this.firstName);
        
        function test() {
            console.log('First Name', this.firstName);
        }
        test();
    }
}

obj.getFullName();
```
## 📘 Arrays (Collections of Anything) 

* Arrays are dyanmically type in javascript

```javascript
var arr = new Array();

// Array Literals 
var arr = [1, 2, 3];

var array = [
    1,                  // number
    false,              // boolean
    {                   // object
        name : 'Tony',
        address : '51 -d street no 3 ranjit nagar'
    },
    function (name) {   // function expression
        var gretting = 'Hello', 
        console.log(greeting + ' ' + name)
    },
    "hello"             // string
];

arr[3](arra[2].name)   // Hello Tony
```
----
## 📘Framework Aside
* *Dangerous Aside :* Automatic Semicolon Insertion, means its not compulsory to add Semicoln at the end of line because javascript do automatically.
* It only occurs in the case of **returns** 
![syntax-parser](https://github.com/amandavid0032/aman/assets/86879390/cef38e6b-96dd-4ffa-9607-fba55fc8bde4)
```javascript
// Problem
function getPerson() {
    return ;
    {
        firstname : 'Tony'
    }
}

// beacuse of automatic semicolon
console.log(getPerson());       // undefined


// Solution
function getPerson() {
    return {
        firstname : 'Tony'
    }
}

console.log(getPerson());       // {firstname : 'Tony'} 
```
* **WhiteSpace :** invisible character that create literal 'space' in your written code. Carriage returns, tabs, spaces.

* javascript remove automatically white space if we provided. 
* White spaces allowed to add comments which make easy to read code. 

```javascript
var 
    // firstname
    firstname,

    //lastname
    lastname,

    // language
    language

var person = {
    // firstname
    firstname : 'john',
    
    // lastname
    lastname : 'Doe'
}
```
---
## 📘Closure

A **closure** is an inner function that has access to the scope of an enclosing function.<br/>

A Closure has access to **variables** in 3 separate Scopes : 
1. Variables in its own scope.
2. Variables in the scope of the outer function.
3. Variables in the global scope.

The closure also has access to __parameters__ :
1. Its own Parameters.
2. Parameters of outer function(s).


```javascript
function greet(whattosay){
return function (name){
 console.log(whattosay+' '+name)
}
}
var say= greet('hello');
say('David');
```
![closures-1](https://github.com/amandavid0032/aman/assets/86879390/b77d30c2-3741-4f27-9444-3288e737bf97)
![closures-2](https://github.com/amandavid0032/aman/assets/86879390/63cca6a5-6a30-47ca-b545-6bb82ec837d3)

```javascript
// Comman Example
function buildFunctions () {
    var arr = [];
    for(var i = 0; i < 3; i++) {
        arr.push(function(){console.log(i)});
    }
    return arr;
}

var fs = buildFunctions();
// all are getting same 3 value because there environment is same means they all are referering to same 'i' variable
fs[0]();    //3
fs[1]();    //3
fs[2]();    //3
```
```javascript
//Solution
function bulid(){
   var arr= [];

   for(var i=0;i<3;i++){
      arr.push( (function(j){
        return function(){
            console.log(j)
         }
      }(i)))
   }
   return arr;
}
var fn=bulid();
fn[0]();
fn[1]();
fn[2]();
```
```javascript
//Example
function outer(outerParam) {
   return function inner(innerParam) {
  
console.log( outerParam + innerParam);
  }
}

var closure = outer(10);
var result = closure(5);
```
📚 **Conceptual Example :** Function Factories Pattern

```javascript
function makeGreeting (langauge) {
    return function (firstname, lastname){
        if(language === 'en') {
            console.log('Hello '+ firstname + ' ' + lastname)
        }

        if(language === 'es') {
            console.log('Hola '+ firstname + ' ' + lastname)
        }
    }
}
// it will create its own execution context even though it have same lexical environment
var greetEnglish = makeGreeting('en');

// it will create its own execution context even though it have same lexical environment
var greetSpanish = makeGreeting('es');

greetEnglish('john', 'Doe');
greetSpanish('john', 'Doe');
```
![function-factories-3 (2)](https://github.com/amandavid0032/aman/assets/86879390/caa7bcb9-5364-4817-9417-08e8d9fe4c11)
![function-factories-3 (1)](https://github.com/amandavid0032/aman/assets/86879390/724d9459-6d09-4249-9cf4-c69aa80f773d)
![function-factories-3](https://github.com/amandavid0032/aman/assets/86879390/29dba807-36aa-4238-a575-f1862a05bd06)
![function-factories-2](https://github.com/amandavid0032/aman/assets/86879390/315c71ba-1210-454c-a2f3-d354f70e0ab3)
![function-factories-1](https://github.com/amandavid0032/aman/assets/86879390/4ccd24ba-4ab2-421e-8ddc-451b8caf9074)
---

## 📘Closures and Callbacks 

* **Callback Function :** A function you give to another function, to be run when the other function is finished. so the function you call (i.e invoke), 'calls back' by calling the function you gave it when it finishes.

```javascript
function tellMeWhenDone(callback) {
    var a = 1000;
    var b = 2000;

    callback();
}

// send function expression
tellMeWhenDone(function() {
    console.log('I am Done !');
})

// send function expression
tellMeWhenDone(function() {
   alert('I am Done !');
})
```
---

## 📘 Call, Apply and Bind Methods

These methods are used to __manipulate__ the __this__ keyword.
![call-bind-apply](https://github.com/amandavid0032/aman/assets/86879390/71bd5a4b-df99-4793-8c0a-c208a71c3922)
```javascript
//example
   let obj1 = {
    firstName : 'Deepinder',
    lastName : 'Singh',
    getFullname : function (city, state) {
        return this.firstName +' '+ this.lastName + ' '  +city +' ' +state; 
    }
   }

   let obj2 = {
    firstName : 'Aman',
    lastName : 'Singh',
   }



console.log(obj1.getFullname.call(obj2, 'patiala', 'punjab'))
console.log(obj1.getFullname.apply(obj2,[ 'patiala', 'punjab']))

let data = obj1.getFullname.bind(obj2);
console.log(data('patiala','punjab'));
```

Mostly used cases <br/>
1. __Function Borrowing__ : Taking function from other


```javascript
let obj1 = {
    firstName: "Aman",
    lastName: "David",
    getFullName() {
        return this.firstName + ' ' + this.lastName
    }
}

let obj2 = {
    firstName: "DavidAman",
    lastName: "Singh"
}

obj1.getFullName.apply(obj2);

```

2. __Partial application__ : Partial refers to partially giving function parameter and then provide all parameter later.

```javascript
function multiply(a, b) {
    return a * b;
}

// window == this

let multiplyByTwo = multiply.bind(window, 2);
multiplyByTwo(4)    // 8

let multiplyByTen = multiply.bind(this, 10);
multiplyByTwo(5)    // 50
```
--- 

## 📘 Object-Oriented Javascript and Prototypal Inheritence (Classical Vs Prototypal Inheritance)
* **Inheritance :** One object gets access to the properties and methods of another object.
* Classical Inheritance :  Verbose.
* Prototypal Inheritance : Simple.

--- 
## 📘 Understanding the Prototype
* **Prototype Chain :** is a chain which allow you to access properties of methods of another object.
![prototype-chain](https://github.com/amandavid0032/aman/assets/86879390/62c6ecc6-1dc2-4160-9273-beec1d52578c)

```javascript
var person = {
    firstName: 'Aman',
    lastName: 'David',
    age: 23,
    getfullName() {
        return this.firstName + ' ' + this.lastName;
    }
}
var john = {
    firstName: 'john',
    lastName: 'Doe'
}

// don't do this EVER! for demo purposes only
john.__proto__ = person;
console.log(john);
console.log(john.age);
```
![Screenshot (195)](https://github.com/amandavid0032/aman/assets/86879390/a2d6b3f4-3256-4df6-91b7-65f680af6da5)

```javascript
var a = [];
var b = '';
var c = 1;
var d = () => { };
var e = true;
var f = {};

a.__proto__ = Array.prototype   // true
```
---
## 📘 Building Objects
1. Object Literals
```javascript
var object = {};
```

2. **Function Constructors :** A Normal function that is used to *construct objects*. The 'this' variables points a new empty object, and that object is returned from the function automatically. 

   1. **new** keyword will create an empty object first, if we do not use **return** keyword it will return empty object other wise normal return value
   2. then **Person('john','Deo')** function will called with values, which help to add new **properties** and **methods** to *newly created object*
   3. then **this** keyword will bind according to the current object by new keyword.

```javascript
function Person(firstname, lastname) {
    this.firstname = firstname;
    this.lastname = lastname;
}

var john = new Person('john','Deo');
var dp = new Person('Deepinder', 'Singh');
```
---

## 📘 Function Constructors and '.prototype'
* **'.prototype' :** property always created automatically  with function constructor only.
* Function Constructors has **first letter** always **capital**
![function-constructor-prototype](https://github.com/amandavid0032/aman/assets/86879390/626e600e-d501-48fd-ac1e-e6ab3588ff5f)
```javascript
function Person(firstname, lastname) {
    this.firstname = firstname;
    this.lastname = lastname;
}

Person.prototype.getFullName = function () {
    return this.firstname + ' ' + this.lastname;
}

var john = new Person('John', 'Doe');
var jane = new Person('Jane', 'Doe');

console.log(john.getFullName());
console.log(john.getFullName == Person.prototype.getFullName)   // true

console.log(john.__proto__ == Person.prototype);    // true
```
⚠️ Why we are adding function into prototype ? 
* beacuse **it save our memory**. When ever we create an object it use memory to store properties and methods, if we storing same method in every object then every object consume very large amount of memory, while creating method using prototype then all objects will refers to that method.
* so for better optimization always add methods to prototype
---
## 📘 Built-in function Constructors

```javascript
var a = new String('Hello');    // here a will become object 
var b = new Array([1,2,3,4]);   // here b will become object 
var c = new Boolean(0);         // here c will become object 
var d = new Number(3);          // here d will become object 

var date = new Date('31/1/2023')// here date will become object

'Hello'.lenght      // String class will create wrapper and produce object.

// Prototype Inheritance Example
String.prototype.isLengthGreaterThan = function (limit) {
    return this.length > limit;
}

// isLengthGreaterThan method will access by all string beacuse of prototype inheritence
console.log("John".isLengthGreaterThan(3))
```

📚 **Conceptual Example :**

```javascript
Number.prototype.isPostive = function () {
    return this > 0;
} 

3.isPostive()   // error  : Unexpected token Illegal

'Hello'.lenght  // no error

// beacuse javascript is not to much smart beacuse javascript convert string into object automatically but not to number

var a = new Number(3).isPostive();  // true
```

**Dangerous Aside :** 

```javascript
var a = 3;             // primitve value 
var b = new Number(3); // b is not number here its a object
var c = Number("3")    // its converting into number 
a == b                 // true 
a === b                // false (number === object) 
```
⚠️ Note : **Moment.js** (is best library for related to dates)
---

---

## 📘Dangerous Side Arrays and for in
In javascript Arrays are objects that is the reason we access property like this 
```javascript
var a = ['aa','bb','cc'];

a[0] // a 

// 0 : Key name & aa : is Value name
```
* For Array always use **simple for loop**
* For Objects always use **for in Loop**

```javascript
Array.prototype.myCustomeFeatures = 'cool!';

var arr = ['john', 'jane', 'jim'];

for(var prop in arr) {
    console.log(prop + ' : ' + arr[prop]);
}

// john
// jane
// jim
// 'cool!'      // it will occur because Array are objects
```
```javascript
//solution

Array.prototype.myCustomeFeatures = 'cool!';

var arr = ['john', 'jane', 'jim','aman','david'];

for(i=0;i<arr.length;i++){
    console.log(arr[i]);
}
```

## 📘 Object.create and Pure Prototypal Inheritance

```javascript

const personPrototype = {
  greet: function() {
    console.log("Hello!");
  }
};

// it will create new empty object and then pointing out this prototype object

const person = Object.create(personPrototype);
console.log(person);     // empty object

// Add Proprerties to the empty object
person.name = "John";
person.age = 30;

console.log(person); // { name :"John", person.age : 30}
```

## 📘ES6 (Ecmascript) and Classes
* Next version of javascript 
* Classes are another way to create Object
* **Syntactic Sugar :** A Different way to type something that doesn't change how it works under the hood.
* at the end, its all Prototypol Inheritance
```javascript
/*
//just like 

function Person (firstName, lastName) {
    this.firstname = firstname;
    this.lastname = lastname
}

Person.prototype.greet = function () {
    return 'Hi ' + this.firstname
}

var john = new Person('john', 'Doe');
*/

class Person {
    constructor(firstname, lastname) {
        this.firstname = firstname;
        this.lastname = lastname;
    }

    greet() {
        return 'Hi ' + this.firstname;
    }
}

var john = new Person('john', 'Doe');

/*
//just like

var InformalPerson.__proto__ = Person;
*/

class InformalPerson extends Person {
    constructor(firstname, lastname) {
        super(firstname, lastname)
    }
    greet() {
        return 'Yo ' + this.firstname;
    }
}
```
---
## 📘 Initialization
```javascript

var a=[
    {
        firstname:'Aman',
        lastname:'david',
        address:[
            '111',
            '222',
        ]
    },
    {
        firstname:'deep',
        lastname:'singh',
        address:[
            '3333',
            '4444',
        ]
    },
    {
        firstname:'amisha',
        lastname:'rani',
        address:[
            '555',
            '666',
        ]
    },
    {
        firstname:'shiven',
        lastname:'oberio',
        address:[
            '7777',
            '8888',
        ]
    }
]
console.log(a[1].address[1]);
```
---
## 📘 Odds and Ends
### 1. typeOf , instanceOf and FiguringOut what Something is
