## 📔 OOPS With PHP

## 📘 Developer Responsibility
* Write good code so everyone can read and understand easily.
* the harder is to understand code and to reason about the code the more difficult it will be to add new features add to more the functionality to the * * * application. Hence it is called bad code.
* An important part of web-development is actually handle the errors. because its very common that errors happen in web-application.
* To test APi use Network tab with various Throttling options fast/slow/offline
---
## 📘 why oops
* Object-oriented programming has several advantages over procedural programming:
* OOP is faster and easier to execute
* OOP provides a clear structure for the programs
* OOP helps to keep the PHP code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug
* OOP makes it possible to create full reusable applications with less code and shorter development time
---
## 📘 What is oops
1. OOPS is about creating classes and objects. Classes serves as a templates and multiple objects can be created using a classes.

2. what are classes and objects : Classes are templates for creating objects. Eg : if car is a class then maruti suzuki alto and maruti swift are two objects 

* Spose in class there are 30 students, now teacher have to show numbers of each students so he can show in two way 
1. make a Template for each student to show marks : called Procedural Programming
2. make a single template and use that single template to show marks by calling functions : Called OOPs programming 

***

**Class**
* a class is a blueprint or template for creating objects. It defines the properties (attributes or fields) and behaviors (methods or functions) that all objects of that class will have. Classes serve as a way to organize and structure code by encapsulating related data and functionality into a single unit.

***

**Object**
* An object is an instance of a class. It is created based on the blueprint provided by the class. Objects have their own unique state (property values) and behavior (methods). You can create multiple objects from the same class, each with its own set of property values.
---
![Screenshot (295)](https://github.com/amandavid0032/Web-Development/assets/86879390/ff194194-7ea2-47b8-8ff1-8bb30b9cdfdf)
---
```Php

class Calu{                                  // Define  class 
  public $a,$b,$c;                          // Properties (variable of current class)    
  function add(){
    $this->c=$this->a+$this->b;
    return $this->c;
  }
  function sub(){
    $this->c=$this->a-$this->b;
    return $this->c;
  }
}
$object=new calu();                        //creating object of the class 
$object->a=20;                             // passing value to parameter
$object->b=30;
echo "sum of to number of object:".$object->add(). "<br/><br/>";    //Calling function 
//Output sum of to number of object:50
$object->a=100;
$object->b=40;

echo "sub of to number of object:".$object->sub();  //calling function
//sub of to number of object:60
```
---
## 📘 PHP Constructor
1.A constructor allows you to initialize an object's properties upon creation of the object.

2.If you create a __construct() function, PHP will automatically call this function when you create an object from a class.

3.Notice that the construct function starts with two underscores (__)! 

4.Reduce the code length
```php
class Person{
public $name;
public $age;
public $email;

function __construct($name="No Name",$age=0,$email="NO Email")    //Define Construct as it 
{
  $this->name=$name;
  $this->age=$age;
  $this->email=$email;
}
function show(){
  echo $this->name."- ".$this->age."- ".$this->email. "<br/>";
}
}
$p1=new Person();
$p2=new Person("Aman",23,"amandavid9956@gmail.com");
$p3=new Person("Harsh",23,"aman@gmail.com");
$p4=new Person("David",23,"david9956@gmail.com");
$p1->show(); // No Name 0 NO Email
$p2->show();//Aman 23 amandavid9956@gmail.com
$p3->show();//Harsh 23 aman@gmail.com
$p4->show();//David 23 david9956@gmail.com

```
---
## 📘 Inheritance
1.It is a concept of accessing the features of one class from another class. If we inherit the class features into another class, we can access both class properties. We can extends the features of a class by using 'extends' keyword.
	
2. It supports the concept of hierarchical classification.

3. Inheritance has three types, single, multiple and multilevel Inheritance.

4. PHP supports only single inheritance, where only one class can be derived from single parent class.

5. We can simulate multiple inheritance by using interfaces.
	
6. The child class will inherit all the public and protected properties and methods from the parent class. In addition, it can have its own properties and methods.

7. An inherited class is defined by using the extends keyword.
---
![Screenshot (296)](https://github.com/amandavid0032/Web-Development/assets/86879390/095bcc43-0ae3-41f5-b0c6-600345d7fe11)
---
```php

//Parent class or Super class 
class employee{
  public $name;
  public $age;
  public $salary;

  function __construct($n="No Name",$a=0,$s="No Deciede"){
  $this->name=$n;
  $this->age=$a;
  $this->salary=$s;
  }
  function info(){
    echo"<h3>Employee Data <h3>";
    echo"Employee Name:". $this->name."<br/>";
    echo"Employee age:". $this->age."<br/>";
    echo"Employee salary:". $this->salary."<br/>";
  }

}
//child class (sub class ) inheriting from employee 
class mangaer extends employee{
  public $ta=4000;
  public $phone=3000;
  public $totalsallary;
  function info(){
    $this->totalsallary=$this->phone+$this->ta+$this->salary;

    echo"<h3>Manger Data <h3>";
    echo"Employee Name:". $this->name."<br/>";
    echo"Employee age:". $this->age."<br/>";
    echo"Employee salary:". $this->totalsallary."<br/>";
  }
}
$el=new employee("Aman",23,10000);
$el->info();
// create instance of mangaer 
$em=new mangaer("David",24,20000);
$em->info();
```
**types of in heritence** 

1. Single 
2. Multiple   (multiple class merging into one single class)
3. Multilevel (when one class extends the other class and this class further becomes the parent of third class and so on. )
4. Diamond    (it is basically a combination of hierarchical and multiple inheritance. )
5. Hierarchical ( When one class becomes parent of many child classes. This makes a tree like structure.)
6. Hybrid     (this is a combination of any type of inheritance.).

***
**basic Defination**

1. Extends : means we can edit the parent function which is extend in the child class , so basically parent class has function that function 
---
## 📘 Access Modifier
Properties and methods can have access modifiers which control where they can be accessed.

**There are three access modifiers:**

1.public - the property or method can be accessed from everywhere. This is default

2.protected - the property or method can be accessed within the class and by classes derived from that class

3.private - the property or method can ONLY be accessed within the class

***
![Screenshot (297)](https://github.com/amandavid0032/Web-Development/assets/86879390/1dede7da-b2b2-4c1d-8e1b-85b378e6a685)

***
```php
//Public Method 

class base{
  public $name; //public property 

  public function __construct($n){ // Constructor method that accepts an argument.
    $this->name=$n; // Assigns the value of the argument to the 'name' property.
  }
  
  public function show(){ // Method to display the value of the 'name' property.
    echo "your name :".$this->name."<br/>"; 
  }
}

$test=new base("Aman Kondal");   //  Your name: Aman Kondal
$test->name="David";  // Overrides the value of the 'name' property with "David". Your name: Aman Kondal
$test->show(); 
```
***
```Php

class base{
  protected $name; // Declares a protected property called 'name' in the class.

  public function __construct($n){ // Constructor method that accepts an argument.
    $this->name = $n; 
  }
  
  public function show(){ // Method to display the value of the 'name' property.
    echo "Your name: " . $this->name . "<br/>"; // Outputs the value of the 'name' property.
  }
}

$test = new base("Aman Kondal"); // Instantiates an object of the 'base' class with the value "Aman Kondal" passed to the constructor.
$test->name="David";  //Fatal error: Uncaught Error: Cannot access protected property base::$name  
$test->show(); 
```
***
```php
//Protected
class base{
  protected $name; // Declares a protected property called 'name' in the class.

  public function __construct($n){ // Constructor method that accepts an argument.
    $this->name = $n; 
  }
  public function show(){ 
 // protected function show(){ Fatal error: Uncaught Error: Call to protected method base::show() from global scope
    echo "Your name: " . $this->name . "<br/>"; // Outputs the value of the 'name' property.
  }
}
$test = new base("Aman Kondal"); // Instantiates an object of the 'base' class with the value "Aman Kondal" passed to the constructor.
//$test->name="David";  //Fatal error: Uncaught Error: Cannot access protected property base::$name  
$test->show(); 
```
***
```Php
// Protected
class base{
  protected $name; // Declares a protected property called 'name' in the class.

  public function __construct($n){ // Constructor method that accepts an argument.
    $this->name = $n; 
  }
   
  protected function show(){ // Method to display the value of the 'name' property.
    echo "Your name: " . $this->name . "<br/>"; 
  }
}
class drived extends base{
public function get(){
  echo "Your name: " . $this->name . "<br/>"; 
}
}
$test = new drived("Aman Kondal"); // Instantiates an object of the 'base' class with the value "Aman Kondal" passed to the constructor.
$test->get();

```
***
```php
// Private
class base{
  private $name; // Declares a private property 

  public function __construct($n){ // Constructor method that accepts an argument.
    $this->name = $n; 
  }
   
  public function show(){ // Method to display the value of the 'name' property.
    echo "Your name: " . $this->name . "<br/>"; 
  }
}
class drived extends base{
public function get(){
  echo "Your name: " . $this->name . "<br/>";  // Undefined property: drived::$name
 }
}

$test = new drived("Aman Kondal"); // Instantiates an object of the 'base' class with the value "Aman Kondal" passed to the constructor.
$test->name="David";  //David
$test->get();

// $test = new base("Aman Kondal"); // Instantiates an object of the 'base' class with the value "Aman Kondal" passed to the constructor.
// $test->name="David";   //Uncaught Error: Cannot access private property base::$name  
// $test->show();
```
---
## 📘 Overriding
* In object-oriented programming, overriding refers to the ability to redefine a method in a subclass that already exists in its superclass. Both the parent and child classes must have a method with the same name and number of arguments. This allows the child class to replace or modify the behavior of the method inherited from the parent class.
```php

class base{
  public $name="parent class"; 
 public function calc($a,$b){
  return $a*$b;
 }
}
class child extends base{
  public $name="child class";
 public function calc($a,$b){
  return $a+$b;
 }
}
$test=new base();
echo $test->name."<br/>"; //parent class
echo $test->calc(20,5)."<br>"; //100
// child method 
$test=new child();
echo $test->name."<br>";  //child class  acces
echo $test->calc(20,5); //25
```
---
## 📘 Abstract Class
1. we use abstract classes when we want to commit the programmer to write a certian class method, but we are only sure about the name of the method, and not the details of how is should be write 

2. An abstarct class is a class that has at least on abstract method 

3. Abstarct methods can only have names and arguments and no other code. thus we cannot create objects out of abstract classes. Insted we need to create child classes that add the code into the bodies of the month and use these child classes to create objects 

4. Classes "extending" an abstract class must implements all of the abstract methods defined in the abstract class.

5.In object-oriented programming, an abstract class is a class that cannot be instantiated on its own and is meant to serve as a blueprint for other classes. Abstract classes are designed to be subclassed, meaning they provide a structure and interface that subclasses must implement.

***
![Screenshot (298)](https://github.com/amandavid0032/Web-Development/assets/86879390/a4e629aa-e296-458e-80de-4f49fab952e8)

***


```Php

abstract class parentClass{
public $name;
abstract protected function calc($c,$d);
}
class childClass extends parentClass{
  public function calc($c,$d){
    echo $c*$d;
  }
}
$test=new childClass();
$test->calc(20,30);  //600
```

***
	
```Php

abstract class school{

	abstract public function getData();

	public function showData(){
		return "hello world <br/>";
	} 
}

class teacher extends school{
	
	public function getData(){
		echo "Hello Teacher <br/>";
	}

	public function getName(){
		echo "Deep <br/>";
	}
}

$obj=new teacher();

echo $obj->getName();  //Deep
echo $obj->showData(); //hello world
echo $obj->getData();  //Hello Teacher
```
---
## 📘 Interfaces
1. An interface is similar to a class except that it cannot contain code.

2. An interface can define method names and arguments, but not the contents of the methods.

3. Any classes implementing an interface must implements all methods defined by the interface.
	
4. A class can implements multiple interfaces.

5. An interface is declared using the "interface" keyword.

6. Interfaces can't maintain Non-abstract methods.

![Screenshot (300)](https://github.com/amandavid0032/Web-Development/assets/86879390/131bf41b-cf72-48ea-bb64-bba570b0b674)

***
```Php

interface parent1{
  function calu($a,$b);
}
interface parent2{
  function sub($c,$d);
}
class childClass implements parent1,parent2{
  public function calu($a,$b){
    echo $a+$b;
  }
  public function sub($c,$d){
    echo $c-$d;
  }
}
$test=new childClass();
$test->calu(20,35); //55
echo"<br/>";
$test=new childClass();
$test->sub(20,15);//5
```
**difference Between Abstract and Interfaces** 

Interface are similar to abstract classes. The difference between interfaces and abstract classes are:

1. Interfaces cannot have properties, while abstract classes can

2. All interface methods must be public, while abstract class methods is public or protected

3. All methods in an interface are abstract, so they cannot be implemented in code and the abstract keyword is not necessary

4. Interface is complete Abstarct Class but abstarct class is practially Abstarct 

5. Interfaces can be extend another interface and implements in the class 

6. We cannot create object of both

7. We can implements many interface in single class but we can only extends one abstract at a time same as Concrete class therefore 

a. multilevel and multilevel inheritance possible in Interfaces

b. multilevel inheritance possible in classes (abstract or Concret class)

---
## 📘 Static Method 
1.Static methods can be called directly - without creating an instance of the class first.

2.Static methods are declared with the static keyword:

3.Static members in a class are properties or methods that belong to the class itself rather than to instances (objects) of the class. 

4.We use self:: insted of $this-> beacuse here we are not creating Objects 

5.To access a static method use the class name, double colon (::), and the method name:

6.when we declare static variables and its values then it will share by all the objects of class. Thus static variables will be assigned memory once rather assigning it to each and every object.


```Php
// Static Properties:
class Example {
    public static $count = 0;

    public function __construct() {
        self::$count++; // Increment the static property count
    }
}

// Accessing the static property without instantiation(object)
echo "Initial count: " . Example::$count . "<br>"; // Output: 0

// Instantiating two objects of Example class
$obj1 = new Example();
$obj2 = new Example();

// Accessing the static property after instantiation(object)
echo "Updated count: " . Example::$count . "<br>"; // Output: 2
```

***

```Php
class Calculator {
    public static function add($a, $b) {
        return $a + $b;
    }

    public static function multiply($a, $b) {
        return $a * $b;
    }
}

// Calling static methods directly without instantiation(object)
echo "Sum: " . Calculator::add(5, 3) . "<br>"; // Output: 8
echo "Product: " . Calculator::multiply(5, 3) . "<br>"; // Output: 15

```
---
## 📘 Traits

1.Traits are used to declare methods that can be used in multiple classes. Traits can have methods and abstract methods that can be used in multiple classes, and the methods can have any access modifier (public, private, or protected).

2.We can use multiple behaviors using multiple trait in single class 

3.Traits are used to declare methods that can be used in multiple classes. Traits can have methods and abstract methods that can be used in multiple classes, and the methods can have any access modifier (public, private, or protected).

4.Traits are declared with the 'trait' keyword and 'use' keyword is use for trait to inheritance

![Screenshot (302)](https://github.com/amandavid0032/Web-Development/assets/86879390/f3c54791-058b-4d95-a645-b8487fc799a8)

***
```Php

trait Getter {
 
    public function get($a, $b, $c) {
        return $a * $b * $c;
    }

    public function set($a, $b, $c) {
        return $a + $b + $c;
    }
}

class Base {
    use Getter; // Using the Getter trait in the Base class

    // Method to perform calculations and output results
    public function calculate($a, $b, $c) {
        // Call the inherited 'set' method from the Getter trait
        $result1 = $this->set($a, $b, $c);
        // Call the 'get' method from the Getter trait
        $result2 = $this->get($a, $b, $c);

        echo "Result of set: $result1<br/>";
        echo "Result of get: $result2";
    }
}

// Create an object of the Base class
$object = new Base();
// Call the calculate method with specific values to perform calculations and output results
$object->calculate(20, 30, 40);
```

***
**Traits Method Overriding**
1.traits don't directly support method overriding as classes do with inheritance. However, you can achieve a similar effect by using a technique called "trait precedence" or "trait method aliasing."

2.To resolve the Conflict between traits when they have same function in all traits then we use 'insteadof' keyword to resolve the issue or we can change the name of function using alias. 
```php

//  Here coding runing with periorty 
trait Getter {
 
    public function hi() {                      // 2 periorty
    echo "hello from getter";
	}

}
class main{
	function hi(){                           // 3 periorty
		echo "hello from main";
	}
}
class Base extends main {
    use Getter; 

    public function hi() {                     // 1 periorty
		echo "hello from Base";  
		}

    }


// Create an object of the Base class
$object = new Base();
$object->hi();   //hello from Base
```

***
**Traits with periort**
```php

//  Here coding runing with 2 traitis 
trait Getter {
 
    public function hi() {                      // 1 periorty
    echo "hello from getter";
	}

}
 trait G{
	public function hi() {                      //  1periorty
		echo "hello from g";
		}
 }

class main{
	function hi(){                           // 2 periorty
		echo "hello from main";
	}
}
class Base extends main {
    use Getter;
    use G;                                
}                                 
 

// Create an object of the Base class
$object = new Base();
$object->hi();   //Fatal error: Trait method G::hi has not been applied as Base::hi, because of collision with Getter::hi 
         	// can't use 2 traits in this to resolve this isssue use insteadof keyword to resolve this issue     
```

***
**Insteadof**
1. Use the `insteadof` keyword to resolve the issue of two traits having the same function and method.

**Use bhot traits**

1.If want to use bhot traits then us `as` keyword its change the name of function and use it 
```php

trait Getter {
 
    public function hi() {                     
    echo "hello from getter";
	}

}
 trait G{
	public function hi() {                
		echo "hello from g";
		}
 }

class main{
	function hi(){                      
		echo "hello from main";
	}
}
class Base extends main {
    use Getter;
    use G{
		// G::hi insteadOf Getter;         //hello from g
	  Getter::hi insteadOf G;             //hello from getter   
		G::hi as Hello;                   //hello from g 
	     
	}                                 
}                                 
 
// Create an object of the Base class
$object = new Base();
$object->hi();
echo"<br/>";  
$object->Hello();             // use bhot function and just change thr name of function 
```
***
```php

trait Getter {
 
    public function hi() {                     
    echo "hello from getter";
	}

}
 trait G{
	public function hi() {                
		echo "hello from g";
		}
 }

class main{
	function hi(){                      
		echo "hello from main";
	}
}
class Base extends main {

    use Getter;
    use G{
		// G::hi insteadOf Getter;         //hello from g
	  Getter::hi insteadOf G;             //hello from getter   
		G::hi as Hello;                   //hello from g 
	     
	}                                 
}                                 
 
// Create an object of the Base class
$object = new Base();
$object->hi();
echo"<br/>";  
$object->Hello();             // use bhot function and just change thr name of function 

```
---
## 📘 Type Hinting
1. In simple word, type hinting means providing hints to function to only accept the given data type.

2. In technical word we can say that Type Hinting is method by which we can force function to accept the desired data type.

3. In PHP, we can use type hinting for Object, Array and callable data type.

set php version to  PHP 7.0 or greater than to use this concept;

it is process to send data to any method with acceptable datatype for example


***
```php
function hello($v){
 echo $v+1;
}
hello("hello");   //Unsupported operand types: string + int

//Done with type hinting 
function hello(int $v){
	echo $v+1;
   }
   //hello("hello");   //hello(): Argument #1 ($v) must be of type int, string given
  hello(4);			 // 5
```
***
```php
function fruits(array $n){
	foreach($n as $name){
		echo "$name <br/>";
	}
}
$na=['mango','banana','popaya','grapes'];
fruits($na);
```
***
```php

class hello{
	public function sayHello(){
		echo "Hello every one <br/>";
	}
}
class Bye{
	public function sayBye(){
		echo "Bye Everyone <br/>";
	}
}

/*
function wow(hello $c)
{				
	
	$c->sayHello();			gives error becasue we are sending object but the method does not exist in hello class so it will make error
							Exception works on this concept
}


$objBye=new Bye();

wow($objBye);

*/

function wow(hello $c){
	$c->sayHello();
}

$objhello=new hello();

wow($objhello);
```
***
```php

class school{
	public function getName(student $names){	// receiving object
		echo '<ul>';
		foreach($names->names() as $name){		// accessing function from object 
			echo '<li>'.$name.'</li>';
		}
		echo '</ul>';
	}
}
class student{
	public function names(){
		return ['Ram','Krishan','Gopal'];
	}
}

class library{

}
$lib=new library();
$stu=new student();
$sch=new school();


$sch->getName($stu);		// sending object
```
---
## 📘 NameScpace 
Namespaces are qualifiers that solve two different problems:

1.They allow for better organization by grouping classes that work together to perform a task

2.They allow the same name to be used for more than one class

3. Namespaces are declared at the beginning of a file using the namespace keyword: 

***
