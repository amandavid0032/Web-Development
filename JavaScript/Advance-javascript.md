# 📔 ES5
## 📘 Developer Resposibilty

Write good code so everyone can read and understand easily
---
## 📘 Javascript
* **Javascript** is a high-level programing language that is primarily used for creating interactive and dynamic webpage.it is a client-side scripting language. It is also single-thread language.<br>
**Dynamic Webpage**---> Is a webpages that display Different Content each time.
---
## 📘 Javascript Engine
* **Javascript** engine is a program that interprets and executes. it is a typically used in web broswer to reader dynamic content and run client-side scripting.<br/>
**Type of engine**<br/>
* v8            ---> Google crome<br/>
* spider Monkey ---> Mozilla<br/>
* javascript    ---> Apple<br/>
* Chakra       ---> Internet explorer
---
## 📘 Problem That Solved In Javascript Engine
* **Cross-Browser Compatibility**-->Different web browser have their own implementation (How program work program setup and run) of javascript.which can load to compatibility (support various web browser identically) issues<br/>
* **Performance**--> Javascript is a interpreted language which means this it can be slower than compiled language such as java and so engine has advanced techniques such as just-in-time(JIT).<br/>
* **Memory Management**--> Javascript engine use garbage collection to automatically free up memory that is no longer being used by javascript code.<br/>
* **Map(Google map)**--> It give problem its work slow because it execute line by line
---
## 📘 Inside The Javascript Engine
![maxresdefault](https://github.com/amandavid0032/aman/assets/86879390/369a3fa1-8763-4a4b-a4c5-82605be4190c)
---
* **The Parser**--> Parsing(Converting) is the process of analyzing the source code, checking it for error and breaking it upto parts
* **The Ast**--> The parsing or parser a data structure called the abstract syntax tree or Ast. Ast is a tree graph of the source code.When you write code in a programming language, it follows a specific syntax defined by the language's grammar rules. The AST breaks down your code into a tree-like structure, where each node in the tree corresponds to a syntactic element of the code. This allows tools to perform various operations on the code, such as parsing, optimizing, and code transformation.
* **Interpreter** --> An Interpreter Directly executes code line by line without requring them to be compiled into Machine language programing it convert the code into **bytecode** interpreter use different strategies to increase performance and parsing the source code and execute it immediately.
* **The Profiler**-->Profiler Check code and this is a monitor.it makes notes on how we can optimize this code how they run 
* **Compiler**--> The Complier work a head it convert the code in one time(It convert all the code in once time). It convert The code into a machine-code  or lower-level form so that they can be read a and executed by a computer.And replace Bite code with optimized code.
---
## 📘 Jit 
* **JIT** stand for `Just-In-Time` JIt is used to improve the performance of executing Javascript code.Jit is the combination of Interpreter and Compiler
It allows the engine to make informed decisions about where and when to apply optimizations based on the actual behavior of the code at runtime.<br/>
![maxresdefault (1)](https://github.com/amandavid0032/aman/assets/86879390/05d360cb-5ee0-48b8-a689-04a478a9e4f2)
---
**How Jit work in javascript**
* **Interpreter**-->When a JavaScript engine encounters a piece of code, it initially interprets it. Interpretation involves executing the code directly by following the JavaScript instructions.
* **Profiling**--> While interpreting the code, the engine gathers information about the code's behavior, such as which functions are frequently executed, which paths are commonly taken, and which data types are used.
* **Compilation**--> Based on the information gathered during profiling, the engine identifies parts of the code that could benefit from optimization. These parts are selected for compilation.
* **Optimization**--> The selected parts of the code are compiled into highly optimized machine code. The optimization process can involve inlining functions, removing unnecessary checks, and applying various performance enhancements.
* **Execution**--> Once the optimized machine code is generated, it replaces the original JavaScript code for the selected parts. The engine executes the machine code directly, which can be significantly faster than interpreting the JavaScript code.
---
## 📘 Memory Heep  And Call Stack
* Memory Heep is a place where to store and write information so that we can use our memory appropriately. In Heep we get reference of the variable
```javascript
const number = 610; // allocate memory for number 
const string  = 'some text'; // allocate memory for string
const human ={ // allocate memory for an object..... and it's values
first: 'aman',
last : 'david' ,
}
 ```
## 📘 call Stack 
* In JavaScript, the call stack is a data structure that keeps track of function calls in your code. It follows a Last In, First Out (LIFO) order, which means that the most recently called function is the first one to be removed from the stack when it completes. Understanding the call stack is essential for debugging and understanding how JavaScript manages the execution of your 
```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}

function sayHello() {
  greet("Alice");
  greet("Bob");
}

sayHello();
```
![jsengine](https://github.com/amandavid0032/aman/assets/86879390/922dbadb-3f2d-4fef-84cd-3b4cdf78d5c7)
---
## 📘 Stack overflow
* Recursion: Recursive functions are functions that call themselves, either directly or indirectly. If the recursion doesn't have a proper termination condition or if it recurses too deeply, it can cause the call stack to fill up with function contexts, eventually leading to a stack overflow.

* Stack Overflow Exception: When the call stack becomes full and can't accommodate any more function calls, it triggers a "stack overflow exception." This is an error that usually results in program termination, as it indicates a serious issue with the program's logic.

* To prevent stack overflows, developers should ensure that recursive functions have a proper base case or termination condition to stop the recursion when a certain condition is met. Additionally, optimizing code to reduce excessive function calls or using iterative solutions instead of recursion when appropriate can also help avoid stack overflow errors.<br/>
---
![OIP (2)](https://github.com/amandavid0032/aman/assets/86879390/bbd0f723-5f76-43ae-afc1-eaf4f2249a93)

---