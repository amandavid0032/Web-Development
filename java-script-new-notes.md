## 📔 ES5
---
## 📘 Developer Responsibility

Write good code so everyone can read and understand easily
---
## 📘 Javascript
javascript is high-level, object-oriented,Multi-paradigm, Programing-language <br/>
* **High-level**== we don't have to worry about complex stuff like memory management.
* **Object-Oriented**== Based on object for storing most kinds of data.
* **Multi-paradigm**==We can use different styles of programing 
* **Programing-language**==instruct computer to do things
<img width="789" alt="role_of_js" src="https://github.com/amandavid0032/Web-Development/assets/86879390/180c971c-815e-40e9-acd9-7bedc9515c3e">

---
## 📘 Linking Javascript Files
```javascript
<head>
<script>
let js="hello";
if(js === "hello") alert("javascript is Fun!");
  
10+23%2-3 // nothing show anything because we dont give command to print the result
 console.log(10+232*4-3);    
     // console is just an enviroment that bulit to execute a small piece of and show results immediately  so 
    </script>
</head>
<body>
    <h1>Hi This is ls 1 </h1> // this line show when alert function is done
</body>  
</html>
```
---
## 📘 Data type
![Screenshot (201)](https://github.com/amandavid0032/Web-Development/assets/86879390/a7159d63-e2a4-4b3e-bf11-bd965c04b755)
![Screenshot (200)](https://github.com/amandavid0032/Web-Development/assets/86879390/008d5f79-e7aa-4bb2-873b-6eed0d08e2e0)
---
```javascript
    
    let a = 'aman';
    console.log(typeof a); //string
    let b = 123;
    console.log(typeof b); //number
    let c = [1, 2, 3, 4, 5, 6];//In JavaScript, arrays are a special type of object. When you use typeof on an array, 
// it will return "object" because arrays are objects that have additional methods and properties specifically designed for working with ordered 
// collections of data.
    console.log(typeof c);
    let e = true;
    console.log(e) //true
    let f;
    console.log(typeof f); // undefine
    console.log(typeof null);  //object


   let email='amandavid@gmail.com';
   email='aman@mail.com';   // soo let used when we sure the that variable value change in future or anytime;
  
   const dob='2000'; // so const value can't be changed in any condition;
  
```
---
## 📘 Type Conversion and coercion
Type Conversion when we manually convert From one type to another
```javascript
const year='2000';
console.log(year+23); //output 200023 in this case the value is not add because year is a string;

const year='2000';
console.log(Number(year)+23); //output 2023 in this case the value is add because Number convert the string into number
```
---

**Type coercion**
```javascript
console.log('25'+'25'+10) // output wll be 252510 because javascript can't convert it into number;

console.log(+'25'+25+'10')  //5010  +'25' attempts to convert the string '25' to a number using the unary plus operator +. It successfully converts '25' to the number 25. 

console.log('25'-'5'-'10') //10 why because the javascript auttomatcal convert the nto number when it is a **-** function 

console.log('25'*'2') // // 50 because it convert it into number and multiply it
```
---
## 📘 DOM (Document Object Model)
* Dom is stand for **Document object model** Structured representation Of Html Documents Allow Javascpit To access Html Elements And style Elements To Manipulate Them (change Text Html attribute  and even css Styles)
![Screenshot (223)](https://github.com/amandavid0032/Web-Development/assets/86879390/3b592518-8c55-4286-851b-7dc200a5c58d)
![Screenshot (225)](https://github.com/amandavid0032/Web-Development/assets/86879390/5d333f0c-d9fb-4ad0-a0ce-e0d140f89138)
![Screenshot (224)](https://github.com/amandavid0032/Web-Development/assets/86879390/77c850f7-1e2e-47a5-9fe9-6af5c7d6f37b)
---
## 📘 Handling Event Listener And  Implementation The Game Logic
```javascript
// know we add a guess number in this code every time when the user predict the number its garneted a  new random number
//  For Random Number we use Match.random()*20 method it give random number every time between 0 to 20 and
// soo on and random give a number in Decemail and convert to decemail into number we use trunc method
let scretNumber = Math.trunc(Math.random() * 20) + 1;
let score = 20;
let highscore = 0;

// Message function
let displayMessage = function (message) {
  document.querySelector(".message").textContent = message;
};
// Event code where the code is start
document.querySelector(".check").addEventListener("click", function () { // for Event addEvent is used
  const guess = Number(document.querySelector(".guess").value);
  console.log(guess, typeof guess);

  //if  there is no input in field
  if (!guess) {
    displayMessage("No number");
  }

  //when palyar guess the right number
  else if (guess === scretNumber) {
    displayMessage("Congurets its Right Number");
    score++;
    document.querySelector(".number").textContent = scretNumber;
    document.querySelector("body").style.backgroundColor = "Green";
  }

  // High socre
  if (score > highscore) {
    highscore = score;
    document.querySelector(".highscore").textContent = highscore;
  }
  // If guess is wrong
  else if (guess !== scretNumber) {
    if (score > 1) {
      displayMessage(guess > scretNumber ? "number to high" : " To low");
      score--;
      document.querySelector(".score").textContent = score;
    } else {
      displayMessage("you Lost the game");
      document.querySelector(".score").textContent = 0;
    }
  }
});

// Again Button 
document.querySelector('.again').addEventListener('click',function(){
  score =20;
  scretNumber =Math.trunc(Math.random()*20)+1;
  displayMessage('Start Guessing...');
  document.querySelector('.score').textcontent =score;
  document.querySelector('.number').textContent='?';
  document.querySelector('.guess').textContent='';
  document.querySelector('body').style.backgroundColor=' #333';
})
```
---
## 📘 This Keyword 
**this keyword/variable**: Special variable that is created for every execution context (every function). Takes the value of (point to) the "owner" of the function in which this keyword is used.<br>
this is Not static. it depends on the how the function is called, and it's value is only assigned when the function actually called.

**Method** this=object that is called the method.<br>
**Simple Function call** this =undefined <br>
**Arrow Function** this  =<this surrounding function(lexical this) > arrow function don't get own this.<br>
**Regular Function** this is undefine when this is in side a method and inside a regular function call which this is clearly is that this keyword is undefine <br>
**Event Listener** this=DOM element that the handler is attached to
```javascript
'use strict';
console.log(this); // "this" is defined in this 

function call(birthyear){
    console.log(2010-birthyear);
    console.log(this); // "this" is not defined in this function

}
call(200);

function Person(name) {
  this.name = name;
}

const person1 = Person('Alice'); // Error in strict mode, "this" is undefined

//Arrow Function 
const name=f=>{ //arrow function has no it's own this keyword it's use lexical environment this keyword
  console.log(2020-f);
console.log(this);
}
name(2010);
```
```javascript

const name = {
  year: 2000,
  call: function () {
    console.log(this);
    console.log(2020 - this.year);
  },
};
name.call(); //In this keyword represenrt to name 
const aman = {
  year: 2017,
};
aman.call = name.call;
aman.call(); //In this keyword represemt to the aman 

```
---
## 📘 Primitives vs. object
![Screenshot (229)](https://github.com/amandavid0032/Web-Development/assets/86879390/b2e70432-19c8-4125-8a2f-329acf3b4c3f)
```javascript
// primitive value which contain single value 
let name='david';
const aname=name;
name='aman';
console.log(name,aname);


//object Wich contain multiple values
const david={
  firstname:'aman',
  lastname:'kondal',
  age:22,
}
const davidafter=david;
davidafter.lastname='david';
console.log(davidafter); 

//copy of the object and but it can't access the  
const aman={
  firstname:'aman',
  lastname:'David',
  age:'23',
  family:['aman','david','deep']
}

const fname=Object.assign({},aman);
fname.lastname='aman';
aman.family.push('vishal')
aman.family.push('simgh')
console.log('before change',aman)
console.log('after change',fname)
```
--- 
## 📘 Destructuring(on Array and Object)
* Destructuring is a feature that is used for unpacking values from the object and array into separate variables
* Into other word destructuring is break complex data-structure down into smaller data structure like a variable
* Destructuring is used to Destructure the values
* Major Differnec beteen Object And Array Destructuring is Order matter in array Destructuring but in Object only name
* Rest Operator is used for get all values and always use at the end  
1. Array Destructuring
* Oder Matter
```javascript
const resturent={
  name:'India Resturent',
   category:['Punjabi','chines','veg','non-veg'],
};
let [first,Third]=resturent.category; //output Punjabi,chines  
let [first, ,Third]=resturent.category // output punjabi,veg 
console.log(first,Third);                   
```
* Simple Example
```javascript
// Main Problem with out destructuring
const array = [1, 2, 3];
const first = array[0];
const second = array[1];
const third = array[2];

// Solution
const array = [1, 2, 3];
const [first, second, third] = array;
```
* Swaping Two Number
```javascript
let a = 10;
let b = 20;
[b, a] = [a, b];
```
* Destructing Nested Array
```javascript
const array = [1, 2, [3, 4]];
const [first, second, [three, four]] = array;
console.log(three);
```
* Default Value
```javascript
const array = [1, 2];
const [first = 1, second = 2, three = 3] = array;
console.log(three);
```
2. Object Destructuring
* First way to destructuring
```javascript
const resturent = {
  resturentName: "India Resturent",
  location: "Punjab chandighar,sec 13 near awm park",
  category: ["Punjabi",'South', "chines", "veg", "non-veg"],
  startmenu: ["breakfast", "lunch", "dinner"],
  mainMenu: ["pizza", "pasta", "rita"],
}
const{resturentName,location,startmenu}=resturent;
console.log(resturentName,location,startmenu);
```
* Aliase name
```javascript
const obj = {
    firstname: "Aman",
    lastname: "David",
    phone: "9914765766",
    address: {
        street: 3,
        houseNo: "24"
    }
}

const { firstname: first, lastname: last } = obj;
console.log(first,last);
```
* Nested Object
```javascript
const obj = {
    firstname: "Aman",
    lastname: "David",
    phone: "9914765766",
    address: {
        street: 3,
        houseNo: "24"
    }
}
const { firstname, lastname, address: { street } } = obj;
console.log(street);
const { firstname, lastname, address: { street } } = obj;
console.log(first);
```
* Providing Default Value (even values does not exist we can provide default value)
```javascript
const obj = {
    firstname: "aman",
    lastname: "david",
    phone: "9914765766",
    address: {
        street: 24,
        houseNo: "301"
    }
}
const { job = "Frontend Engineer" } = obj;
console.log(job);
```
* Using Rest Operator for getting other values
```javascript
const resturent = {
  name: "India Resturent",
  location: "Punjab chandighar,sec 13 near awm park",
  category: ["Punjabi", "chines", "veg", "non-veg"],
  startmenu: ["breakfast", "lunch", "dinner"],
  mainMenu: ["pizza", "pasta", "rita"],
  openingHours: {
  mon: {
      open: 12,
      close: 7,
    },
    tue: {
      open: 12,
      close: 7,
    },
    wed: {
      open: 12,
      close: 7,
    },
    thu: {
      open: 12,
      close: 7,
    },
  },
offer:{
  combo:2000,
  family:3000,
  unlimited:5000,
}
};
const{name,openingHours:{mon},offer:{unlimited},...other}=resturent
console.log(name,mon,unlimited,other);
```
* Mutating variables
```javascript
let a = 222;
let b = 444;
let c = 345;
const obj = {
  a: 1,
  b: 2,
  c: 3,
};
({ a, b, c } = obj);
console.log(a, b, c); //1,2,3
```
## 📘 Spread Operator
* Basically use to expand an array into all its elements,so basically unpacking all the array element at one.
* Spread operators work with both **iterables** and objects  
* All the data structures in Javascript are iterables eg arrays, strings, maps, sets but Not Objects . 
* Spread operator is only used when building an array or when we pass values into a function
* Spread operator do this
```javascripts
const arr = [1, 2, 3];
console.log(..arr)  // (1, 2, 3)
```
* Iterables
```javascript
const varibale='Aman David';
const latter=[...varibale,'','Kondal'];
console.log(latter); // ['A', 'm', 'a', 'n', ' ', 'D', 'a', 'v', 'i', 'd', '', 'Kondal'] each latter of string element expend it.

console.log(`${...varibale} hello`); //error because it is not a place where we expects multple vales sperated by a comma
// only work when we pass an arrguments into function or when we build an new array
```
* Problem why we use Spread operator
```javascript
// Problem
const arr = [7, 8, 6];
const badNewArr = [1, 2, arr[0], arr[1], arr[2]];
console.log(badNewArr); //[1, 2, 7, 8, 6]

// Solution (creating new array)
const arr = [7, 8, 6];
const badNewArr = [1, 2, arr[0], arr[1], arr[2]];
console.log(badNewArr); //[1, 2, 7, 8, 6]

// Solution (creating new object)
const obj = {first : 'Aman'}
const obj1 = {...obj, last : 'David'}
console.log(obj1);
```
* Join 2 Array
```javascript 
const arr=[1,2,3,4,5,6];
const newArr=['Aman','Dav',9];
console.log(...arr,...newArr); // output 1 2 3 4 5 6 'Aman' 'Dav' 9
```
---
## 📘 Rest Operator
* The spread operator is to unpack an array while rest operator is to pack elements into an array
* For Arrays 
```javascript
// spread because on right side of =
const arr = [1, 2, ...[3, 4]];

// Rest because on the left side of =
const [a, b, ...others] = [1, 2, 3, 4, 5];
console.log(a, b, others);
```
* For Objects
```javascript
let obj = { first: 'Deepu', last: 'Singh', phone: '9915099247' };
const { first, ...others } = obj
console.log(first);
console.log(others);
```
* For Function
```javascript
function sum(...numbers) {
     // its now array
    console.log(numbers);
}
sum(1, 2, 3, 4, 5, 6, 7, 8, 9);
```
```javascript

function test (...variable){
 const [newVariable,...other]=variable;
  console.log(newVariable,other)
}
test(1,2,3,4,5,6);
```
---
## 📘Short Circuit
* OR Operator (||) : it will return true value always
```javascript
undefined || null || '' || false || 0 || 'Hello' || 23  // 'Hello'
false || 'hello' || 'aman' || 23   // hello
'test' || 'ok'  // test
'' || 'ok'  // ok
```
* AND Operator (&&) : it will return false value if the first value is false, it works opposite to OR Operator
```javascript
0 && 'jonas'    // 0
1 && 'Aman'    // Aman
true && 0 && '' && hello   //0
'hello' && 23 && null && 'jonas'    // null
```
---
## 📘 Nullis
* Only check null or undefined value
* Not include 0 (zero) or "" (empty string)
```javascript
const test = 0;
console.log(test || 'Hello');   // hello

// Nullish : null and undefined (Not 0 or '')
console.log(test ?? 'Hello');   // 0
```
---
## 📘 Enhanced Object
* "Enhanced Object Literals" in JavaScript, which is a feature introduced in ECMAScript 6 (ES6).
*  Enhanced Object Literals provide a more concise way to define and work with objects. 
* Method Definitions:
```javascript

const myObject = {
  myMethod() {   //also Wrtie a Function lie this in object
    // Method implementation
  }
};
```
* Computed Property Names:
```javascript
const weekend=['mon','tue','wed','thur','fri','satu','sun'];   //write a (array) property name outside the object and access in side
const offer={              //Also write a object outside the object and access inside 
  combo:2000,
  family:3000,
  unlimited:5000,
}
const resturent = {
  name: "India Resturent",
  location: "Punjab chandighar,sec 13 near awm park",
  category: ["Punjabi", "chines", "veg", "non-veg"],
  startmenu: ["breakfast", "lunch", "dinner"],
  mainMenu: ["pizza", "pasta", "rita"],
  openingHours: {
  [weekend[0]]:{
      open: 12,
      close: 7,
    },
    [weekend[1]]: {
      open: 12,
      close: 7,
    },
},
offer
};

const { name, openingHours, offer: { unlimited }, ...other } = resturent;
console.log(name, openingHours[weekend[0]], unlimited, other);
```
---
## 📘 Other Data-structure (ES6)
1.**Set:**
* A collection of unique values, so that means that a set can never have any duplicates. (its kind of array not exactly array)
* Actual use is to remove duplicate values from arrays.
* In set order does not matter, hence we cannot access values by using index. only use to check the values exist or not.
* Set are iterable.
```javascript

const newSet=new Set(['aman','David','aman','David','deep','kondal']);

console.log(newSet); //{'aman','David','deep','kondal'}

console.log(newSet.size); // 4 It's tell the size of the the set don't include the duplicate values

console.log(new Set('Aman')); //{'A','m','a','n'}

//Checking for Key Existence:
console.log(newSet.has('nitick')); //false check that the value exit or not and return bollen

console.log(newSet.add('amish'));// {'aman', 'David', 'deep', 'kondal', 'amish'} add 

//Removing Key-Value Pairs:
newSet.delete('aman'); //{'David', 'deep', 'kondal', 'amish'} Delete

//Clearing the Set
newSet.clear('aman'); // {size:0} Delete all the values in set 

// Actual Real Example of Set
const oderSet=new Set(['aman','David','aman','David','deep','kondal']); 
const set=[...new Set(oderSet)]; // also use the spread operator
console.log(set);  // ['aman', 'David', 'deep', 'kondal'] create a array
```
2.**Maps:**
* its like Objects but the major difference is that, in objects the keys are basically always strings, but in maps we can have any type of key. it could even be objects, or arrays or other maps.
```javascript
// 1. Creating Map in this way

const rest = new Map()  // always create empty map here
rest.set('name', 'Aman');
rest.set(1, 'web-developer');
rest.set(true, 'apple')


console.log(rest.get(arr)); // array value
console.log(rest.get(1));   //web-developer
console.log(rest.get('1')); // undefined

console.log(rest.has(true));    // true
console.log(rest.has('test'));  // false

console.log(rest.size);     // 3


// 2. Creating Map in this way

const question = new Map([
    ['question', 'what is the best programming language in the world'],
    [1, 'c'],
    [2, 'java'],
    [true, 'correct'],
    [false, 'Try Again']
]);

console.log(question)   //  {'question' => 'what is the best programming language in the world', 1 => 'c', 2 => 'java', true => 'correct', false => 'Try Again'}

 for (let [key, value] of question) {
    console.log(key + ' : ' + value);
}

// question : what is the best programming language in the world
// 1 : c
// 2 : java
// true : correct
// false : Try Again

// Converting into array once again
const array = [...questions];

// map Method Return new array with new element it's Don't Muttate the array  
const movementstest=[5000, 3400, -150, -790, -3210, -1000, 8500, -30];
const Usd=77.1;
const movementsUSD=movementstest.map(function(mov){
return  Math.trunc(mov*Usd); 
})
console.log(movementstest);
console.log(movementsUSD);
```
---
## 📘  Source Of Data
![arrays-vs-set-object-vs-maps](https://github.com/amandavid0032/Web-Development/assets/86879390/6700e8f3-ecb5-410c-b7bc-115cc53a10b4)
![source-of-data](https://github.com/amandavid0032/Web-Development/assets/86879390/3a8b933f-c6b4-4c4e-a0a6-abe0ae74e296)
---
## 📘 String & String Method
* Method
1. indexOf
2. lastIndexOf
3. slice
4. splice
5. includes
6. replace
7. toLowerCase
8. toUpperCase
9. split
10. join
11. at(1) & at(-1)
12. padStart & padEnd

* Example
```javascript
let firstname = "Aman David";

console.log(firstname[0];)   // A
console.log(firstname[1];)   // m
console.log(firstname[2];)   // a
```  
```javascript
console.log('I am Web Developer'[0]);   // I
console.log('I am Web Developer'[2]);   // a
console.log('I am Web Developer'.length);   // 18

// Methods
// 1. indexOf
console.log('I am Web Developer'.indexOf('a'));   // 2
console.log('I am Web Developer'.indexOf('Web')); // 5

// 2. lastIndexOf
console.log('I am Web Developer'.lastIndexOf('Web')); // 5
console.log('I am Web Developer'.lastIndexOf('e'));   // 16

// 3. slice
console.log('I am Web Developer'.slice(3));    // m Web Developer
console.log('I am Web Developer'.slice(3, 7)); // m We

// 4. includes
console.log('I am Web Developer'.includes('Web'));  // true
console.log('I am Web Developer'.includes('test')); // false

//Replace
console.log('Aman David'.replace('David','Kondal')); // Aman Kondal

//Trim

const email='amandavid9956@gmail.com';
const newEmail='       amandavid9956@gmail.com';
const trimEmail=newEmail.trim();
console.log(trimEmail);
console.log(email);

// padstart 
const str = 'Hello';
const paddedStr = str.padStart(10, 'X');
console.log(paddedStr); // Output: "XXXXXHello"

//padEnd
const str = 'Goodbye';
const paddedStr = str.padEnd(10, '-');
console.log(paddedStr); // Output: "Goodbye---"


```
---
## 📘 Functions and Default Parameters
```javascript
const bookings = [];
const createBooking = function (
    flightNum=1,
    numPassengers = 1,
    price = 199 * numPassengers
) {
    console.log(flightNum, numPassengers, price);
};

createBooking('LH1')
createBooking('LH1', 3);
createBooking('LH1', undefined, 2);

```
⚠️ Note : ?????
Dought so Don't Write topic
---
## 📘 Call, Apply And Bind Method
* In JavaScript, the call, apply, and bind methods are used to manipulate the value of the _**this**_ keyword within a function and allow you to pass arguments to the function. These methods are often used in situations where you want to control the context in which a function is executed.

***

* **Call**
1. The call method allows you to call a function with a specified this value and individual arguments.
2. It takes the context (the object that should be used as this) as its first argument, followed by the arguments to be passed to the function.
3. The function is immediately invoked.
```javascript
const quatarAirline = {
    airline: 'Quatar Airline',
    booking: [],
    bookingNumber: 'DDH9914',
    book(flightNum, name) {
      console.log(`${name} book is set on ${this.airline} Booking Number: ${this.bookingNumber} Flight: ${flightNum}`);
      this.booking.push({ flight: `${flightNum} ${this.airline}`, name });
    },
  };
  quatarAirline.book('DDSU','David');
const book=quatarAirline.book;
indianAirline={
airline:'Indian Airline',
booking:[],
bookingNumber:'AAGH991456',
};

book.call(indianAirline,'AAH4456','Aman');
console.log(indianAirline);

jetAirline={
    airline:'Jeet Airline',
    booking:[],
    bookingNumber:'AAGH991456',
    };
book.call(jetAirline,'BBH1234','Deep');
console.log(jetAirline);

// output
// David book is set on Quatar Airline Booking Number: DDH9914 Flight: DDSU
// Aman book is set on Indian Airline Booking Number: AAGH991456 Flight: AAH4456
// {airline: 'Indian Airline', booking: Array(1), bookingNumber: 'AAGH991456'}
// Deep book is set on Jeet Airline Booking Number: AAGH991456 Flight: BBH1234
// {airline: 'Jeet Airline', booking: Array(1), bookingNumber: 'AAGH991456'}
```

***
* **Apply Method**
1. The apply method is similar to call, but it takes an array or an array-like object as the second argument, which is used as the list of arguments for 
    the function.
2. It is useful when you have an array of arguments to pass to a function.
```javascript
const flightData=['BBAS9987','Amisha'];
book.apply(jetAirline,flightData);
console.log(jetAirline)

// output
// Amisha book is set on Jeet Airline Booking Number: AAGH991456 Flight: BBAS9987
// {airline: 'Jeet Airline', booking: Array(2), bookingNumber: 'AAGH991456'}
```

***
* **Bind Method**
1. The bind method is used to create a new function with a specified this value, without invoking the function immediately.
2. It returns a new function that, when called, will have the specified this value.
```javascript

const quatarAirline = {
    airline: 'Quatar Airline',
    booking: [],
    bookingNumber: 'DDH9914',
    itiacode:'LH',
    book(flightNum, name) {
      console.log(`${name} book is set on ${this.airline} Booking Number: ${this.bookingNumber} flight:${this.itiacode}${flightNum}`);
      this.booking.push({ flight: `${flightNum} ${this.airline}`, name });
    },
  };
  quatarAirline.book('DDSU','David');
const book=quatarAirline.book;

const bookEm=book.bind(quatarAirline,23);   // also set the value that can't be changed
bookEm('Aman');
bookEm('deep');
bookEm(23,'Kondal')
```
---
## 📘 IIFEs
* Immediately Invoked Function Expressions - A function that is executed right after it is created.
* This function run once means not get store any where so we cannot call at any instance.
```javascript

(function(){
  console.log('this will run one time');
  const it=23;
  })();   //it's not define because it scope it private

  (()=>console.log('this run one time and never run again'))();
  {
    const it=23;
    var ittt=23;
  }
  console.log(it);    //output not Defimed
  console.log(ittt);

  // function are special objects, here we are creating function object and function has sepcial property that '() invoking a function' hence called IIFE
(function doubleNumber(num){
  return num * 2;
}(5));  // 10

// Function object get called
var greeting = function(name) {
  return 'Hello' + name;
}('Tony');
console.log(greeting)       // Hello Tony
```
---
## 📘 Closure 
* closure is an inner function that has access to the scope of an enclosing function.
* we don't create closure manually like we create a new array or a new function so a closure simply happens automatically in certain situations, we just need to recognize those situations.

* Closure has access to variables in 3 separate Scopes :
1. Variables in its own scope.
2. Variables in the scope of the outer function.
3. Variables in the global scope.
```javascript
function outerFunction() {
  var outerVar = 10;

  function innerFunction() {
    console.log(outerVar); // innerFunction can still access outerVar
  }

  return innerFunction;
}

var closure = outerFunction();
closure(); // This will log 10, even though outerFunction has finished executing.

```
![Screenshot (239)](https://github.com/amandavid0032/Web-Development/assets/86879390/0e16a034-f295-4a25-aca4-664dbe29da98)
* The closure also has access to parameters :
1. Its own Parameters.
2. Parameters of outer function(s).

```javascript
function greet(whattosay){
    // it return function object which is created on fly
    return function (name) {
        console.log(whattosay + ' ' + name)
    }
}
var sayHi = greet('Hi');
// then we are invoking a function
sayHi('Tony');
```
![closures-1 (1)](https://github.com/amandavid0032/Web-Development/assets/86879390/a299cc6a-3824-44da-8f8a-54b43a1017ec)
![closures-2 (1)](https://github.com/amandavid0032/Web-Development/assets/86879390/d2551c56-4247-4707-9814-667072d32b84)

```javascript


const secureBooking =function(){
let pasengercount= 0;
return function(){
  pasengercount++;
  console.log(`${pasengercount}: pasenger`)
}
}
const booker=secureBooking();
booker();
booker();
booker();
// 1: pasenger
// 2: pasenger
// 3: pasenger
```
![Screenshot (234)](https://github.com/amandavid0032/Web-Development/assets/86879390/f16323eb-7300-4011-9ee1-efade409a5af)
![Screenshot (243)](https://github.com/amandavid0032/Web-Development/assets/86879390/6978a852-9924-4bfd-94ea-1e76b60ae1cf)
![Screenshot (245)](https://github.com/amandavid0032/Web-Development/assets/86879390/1d614f2f-684e-4327-a2b9-a5cbca0a4753)
![Screenshot (246)](https://github.com/amandavid0032/Web-Development/assets/86879390/b6a79442-dfc7-4e35-a39d-ab9a6499c08a)
![Screenshot (247)](https://github.com/amandavid0032/Web-Development/assets/86879390/b4cdcaff-0715-4634-9cd3-836e2f55bd1f)
***
⚠️ Note : conceptual Example
```javascript
let f;
const a=function(){
  const s=23;
 f= function(){
 console.log(s*44);
}
}

const h= function(){
  const b=777;
  f= function(){
    console.log(b*44);
   }
}
a();
f(); //1012
//Re-assigning f function
h();
f(); //34188
```
---
## 📘 Array & Array Method
1.  slice
2.  splice (mutate original)
3.  reverse (mutate original)
4.  join
5.  at(1) & at(-1)
6.  Map
7.  Filter
8.  Reduce
9.  Sort
10. some (return true/false)
11. every (return true/false)
12. include (return true/false)
13. indexOf (return index)
14. find (return value)
15. findIndex(return value index)
16. flat
17. flatMap
18. new Array(7).fill(1)

* Slice
```javascript
// slice Don't Mutate a Array
const arr=[1,2,3,'aman','david','1234',5,6];
console.log(arr.slice(4));   //['david', '1234', 5, 6] 
console.log(arr.slice(2,4)); //[3, 'aman']
console.log(arr.slice(-2));  //[5, 6]
console.log(arr.slice(1,-3)); // [2, 3, 'aman', 'david']
console.log(arr.slice()); // [1, 2, 3, 'aman', 'david', '1234', 5, 6] sallow copy of array
```
* Splice
```javascript
//change the original array  so it mutates that array
arr.splice(-1)
console.log(arr); //[1, 2, 3, 'aman', 'david', '1234', 5]
arr.splice(3,4);  
console.log(arr); //[1, 2, 3]
```
* Reverse
```javascript
//REVERSE also mutates the array
console.log(arr.reverse(arr)); // [3, 2, 1]
```
* CONCAT
```javascript
arr2=['Deep','Amisha',9,8,7];
const letter =arr.concat(arr2);
console.log(letter) // [3, 2, 1, 'Deep', 'Amisha', 9, 8, 7]
```
* JOIN
```javascript
console.log(letter.join('.')); //3.2.1.Deep.Amisha.9.8.7
```
* AT Method
```javascript
//NEW AT METHOD
const newArr=[1,2,3,4,5,6,7,8,9];
console.log(newArr[6]); //7  
console.log(newArr.at(6,2)) //7 Both are working same 
console.log(newArr.at(-1))
```
* Map 
```javascript
const news=new Map(
[  [1,'Hello Aman'],
  ['Aman','Patiala'],
  ['Patiala','Punjab'],
  [true,'Yes its is true'],
  [false,'Yes its is false' ],
])
news.forEach(function(value,key,map){
  console.log(`${key} ${value}`)
})
// Aman Patiala
// Patiala Punjab
// true Yes its is true
// false Yes its is false
```
* Set
```javascript
// Set are no keys And index  
const set=new Set(['Aman','David','Kondal','Aman','David','Deep'])
set.forEach(function(value,key,map){
  console.log(`${key} ${value}`)
})

// Aman Aman
// David David
// Kondal Kondal
// Deep Deep
```
* Sort
```javascript

//Sort
const newArr=['David','kondal','Natick','Aman','Abb']
console.log(newArr.sort());

const Arr=[1,6,5,2,3,0,7,8,9,4];
//Dessending Oder
Arr.sort((a,b)=>b-a);
console.log(Arr); // [9, 8, 7, 6, 5, 4, 3, 2, 1, 0]

//Assending Oder
Arr.sort((a,b)=>a-b);
console.log(Arr); // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
* Flatten Array
```javascript
const arr=[[1,5,2,,18,21,3,4],[0,7,8,9,10],11,12,13];
console.log(arr.flat()); // [1, 5, 2, 18, 21, 3, 4, 0, 7, 8, 9, 10, 11, 12, 13]

console.log(arr.slice(2)); // [11, 12, 13]

console.log(arr); //  [Array(8), Array(5), 11, 12, 13]

var arr = [1, [2, [3, [4, [5, [6, [7, 8, [9, 10]]]]]]]];
var result = arr.flat();
console.log(result);  // [1, 2, Array(2)]

var result = arr.flat(Infinity);
console.log(result); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

var z=new Array(8).fill(1);
console.log(z);

var z = Array.from({ length: 10 }, (paremeter, i) => i+1);
console.log(z);

```
* Creating & Filling Array
```javascript

const s = new Array (7);
console.log(s);
s.fill(1,3,6)
console.log(s) 

var z=new Array(8).fill(1);
console.log(z);

var z = Array.from({ length: 10 }, (paremeter, i) => i+1);
console.log(z);
```
* Some
```javascript
// Return True or false
const movements = [200, 450, -400, 3000, -650, -130, 70, 1300];
const anydeposite=movements.some(mov=>mov>100000);
console.log(anydeposite)   // false
```
* Every
```javascript
// True where all the condition turein array

const x=[1,2,3,4,566,77567];
const everycheck1=x.every(mov=>mov>0);
const everycheck=movements.every(mov=>mov>0);
console.log(everycheck); //false
console.log(everycheck1)
```
![Screenshot (250)](https://github.com/amandavid0032/Web-Development/assets/86879390/1cf6933a-a45f-4d0b-aaa9-d73a257abed6)

* Filter
```javascript
// It's pick out only elements that meet  ceratin condition and creates a new array with elements that pass a test    
const movements = [200, 450, -400, 3000, -650, -130, 70, 1300];
const deposits=movements.filter(function(mov){
  return mov>0;
});
console.log(deposits);  
```
* 



* Find
```javascript
```
---
## 📘 Dates and Times
* create Date
```javascripts
let now = new Date();
console.log(now);
//Tue Jan 02 2024 21:28:47 GMT+0530 (India Standard Time)

now = new Date('Jan 2,2024');
console.log(now);
//Tue Jan 02 2024 00:00:00 GMT+0530 (India Standard Time)

now = new Date('December 24, 2015');
console.log(now);
//Thu Dec 24 2015 00:00:00 GMT+0530 (India Standard Time)
```
* Get Date Paramters : getMethods()
```javascript
const d = new Date();
console.log(d.getDate());
console.log(d.getMonth());
console.log(d.getFullYear());
console.log(d.getHours());
console.log(d.getMinutes());
console.log(d.getSeconds());
console.log(d.toLocaleString());
console.log(d.getTime());
console.log(Date.now());
```
* Set Date Parameters : setMethods()
```javascript
// Set Month
const d = new Date();
d.setMonth(1);
console.log(d);
//Tue Feb 07 2023 15:56:57 GMT+0530 (India Standard Time)

// Set Date
const date = new Date("june 21 2017");
// Adding One Day in given Date
date.setDate(date.getDate() + 1)
// Subtracting One Day in given Date
date.setDate(date.getDate() - 1)
date.toDateString()

// Set Minute
const c = new Date();
c.setMinutes(c.getMinutes() + 2);
let t = c.getTime();
console.log(t)
```
* Show data according to Countries like date format, current format, time, 5 days ago etc
 1.  Dates : day, month, year, hours, minuts, seconds, date, weekend, week,
  And also change date according to the region(like us assia etc)  
```javascript
/*
US English      en-US
British English en-GB
Korean          ko-KR
Arabi           ar-EG
Japanese        ja-JP-u-ca-japanese
Balinese        ban", "id  
*/  
let now = new Date();
let d = new Intl.DateTimeFormat('en-US', {
    hour: 'numeric',
    minute: 'numeric',
    day: "numeric",
    month: "long",
    year: "2-digit",
    weekday: "long"
});
console.log(d.format(now));

// Friday, January 5, 24 at 8:21 PM


// Simple
const f = new Intl.DateTimeFormat('en-us', {
})
console.log(f.format());        // 1/5/2024

Simple
const f = new Intl.DateTimeFormat('en-us', {
    dateStyle: "full",
    timeStyle: "full"
})
console.log(f.format());        // Friday, January 5, 2024 at 8:25:55 PM India Standard Time

// Complex One
const today = new Date();
console.log(today.toLocaleString());    // 5/1/2024, 8:26:15 pm

const f = new Intl.DateTimeFormat('en-us', {
    dateStyle: "full",
    timeStyle: "full"
    // dayPeriod: "long"
})

console.log(f.format());   // Friday, January 5, 2024 at 8:27:01 PM India Standard Time
```
* Relative Time
```javascript
const f = new Intl.RelativeTimeFormat('en-us', {
    style: "long"
})
console.log(f.format(-4, "days"))
```
2.Numbers : currency, style, units, useGroping
```javascript
// Simple Representation
const number = 1111122223333444.1;
const f = new Intl.NumberFormat("en-us", {
    currency: 'USD',
    style: "currency"
})

console.log(f.format(number));  // $1,111,122,223,333,444.10


// Compact Representation

const number = 11133444.1;
const f = new Intl.NumberFormat("en-us", {
    notation: "compact"
})

console.log(f.format(number));          // 11M  (Million)
```