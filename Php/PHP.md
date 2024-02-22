## 📔 ES5
---
## 📘 Developer Responsibility

## What is Php
* PHP is an acronym for "PHP: Hypertext Preprocessor"
* PHP is a widely-used, open source scripting language
* PHP scripts are executed on the server
* PHP is free to download and use 
* PHP is server Side Script language
---
## 📘 Echo And Print
* Echo is faster and accepted Multiple arguments
* Echo return string 
```Php
$var ="Aman";
echo 'Hello $var how are you  <br/>'; //singel quotes does not return value of variable 
// Hello $var how are you
echo "Hello $var how are you <br/>" ; // dubble quotes return variable value 
//  Hello Aman how are you
$result = echo "Hello, World!"; // Error
```
**Print**
* Print return value 1 and it's slower than echo and can't take multiple parameter 
```Php
$result = print "Hello, World!<br/>"; // Valid, $result will be 1 Hello, World!
$result = print "Hello, World!";"aman"; // Hello, World! 
```
---  
## 📘 Constant variable
 * In PHP, constants are like variables, but once they are defined, their values cannot be changed or redefined during the script's execution. Constants are case-sensitive by default, and their names traditionally use uppercase letters.
* It's important to note that constants are accessed without the dollar sign ($) unlike variables. Additionally, constants are global, meaning they can be accessed from any part of the script.
```Php
define("num","My Name is aman Kondal<br/>");
echo num;

define("Variable","My Name is aman Kondal",true);
echo VARIABLE;  
```
---
## 📘 Ternary Operator
*The ternary operator is a shorthand way of writing an if...else statement in PHP. It allows you to write a concise, one-liner conditional expression.
```Php
(condition) ? true_expression : false_expression;
// If the `condition` is true, the expression evaluates to `true_expression`.
// If the `condition` is false, the expression evaluates to `false_expression`.
```
```Php
$age = 25;
// Ternary operator
$message = ($age >= 18) ? "You are an adult." : "You are a minor.";
echo $message; // Output: You are an adult.
```
---
## 📘 While Loop && Do While Loop
**While**
* In PHP, the while loop is used to repeatedly execute a block of code as long as a specified condition is true. The basic syntax of the while loop is as follows:
```Php
$count = 1;

while ($count <= 5) {
    echo $count . " ";
    $count++;
}
```
**Do While**
* In a do...while loop the condition is tested AFTER executing the statements within the loop. This means that the do...while loop will execute its statements at least once, even if the condition is false
```Php
$i = 8;

do {
  echo $i;
  $i++;
} while ($i < 6);
```
----
## 📘 Nested Loop
* In PHP, a nested loop is a loop inside another loop. You can have various combinations of nested loops, such as a for loop inside a while loop or vice versa. Nested loops are useful when you need to perform repetitive tasks within the context of an outer loop.
```Php
for($i=0;$i<10;$i++){
    for($b=0;$b<$i;$b++){
        echo"*";
    }
    echo"<br/>";
}
//Output
// *
// **
// ***
// ****
// *****
// ******
// *******
// ********
// *********
```
---
## 📘 Pass By Value && Pass By Reference 
**pass By Value**
* By default, PHP uses pass by value.
* When you pass a variable to a function, a copy of the variable's value is created, and the function works with this copy.
* Changes made to the variable inside the function do not affect the original variable outside the function. 
```Php
function wow($a){
    $a='Aman';
}
$str='hi';
wow($str);
echo"$str"; //output hi
```
**Pass By Reference**
* If you want a function to modify the original variable, you can pass it by reference using the & symbol in the function definition.
* This means that the function receives a reference to the original variable, and changes made to the variable inside the function affect the original 
  variable.
```Php

function wow(&$a){   //& Symbal is thr defination of pass by reference
    $a='Aman';
}
$str='hi';
wow($str);
echo"$str";  //output Aman
```
---
## 📘 PHP Recursive Function
* A recursive function in PHP is a function that calls itself during its execution. Recursive functions are often used in problems that can be broken down into smaller
```Php
function factorial($n)
{
    if ($n <= 0) {
        return 1;;
    } else {
        return $n * factorial($n - 1);
    }
}
$a = factorial(5);
echo $a; //output 120
```
## 📘 Global & Local Variable
**Global Variable**
* Global variables are declared outside of any function or class.
* They can be accessed from any part of the script, both inside and outside functions or classes.
* To declare a global variable, you can use the global keyword followed by the variable name within a function to indicate that you want to access the 
  global variable, not create a local one.
```Php
$globalVar = "I am a global variable.";

function accessGlobalVar() {
    global $globalVar;
    echo $globalVar;
}

accessGlobalVar(); // Output: I am a global variable.
```
**Local Variable**
* Local variables are declared within a function or a block of code and are only accessible within that specific scope.
* They are not visible or accessible outside the function or block in which they are declared.
```Php
function localVariableExample() {
    $localVar = "I am a local variable.";
    echo $localVar;
}

localVariableExample(); // Output: I am a local variable.

// Attempting to access $localVar outside the function will result in an error.
// echo $localVar; // This would result in an "Undefined variable" error.
```
---
## 📘 Array 
* an array is a data structure that stores a collection of elements, each identified by an index or a key. The elements in an array are typically of the same data type, and they are stored in contiguous memory locations.
```php
$names = array('John', 'Jane', 'Bob');
```
**Array Types**
**Indexed Arrays**
* Also known as numeric arrays.
* Elements are accessed using numeric indices.
* Indexing usually starts from 0.

```Php
 $numbers = [1, 2, 3, 4, 5];
```
**Associative Arrays**
* Elements are accessed using named keys instead of numeric indices.
* Allows for more descriptive and meaningful indices.
```Php
// Example 1
$person = array("name" => "John", "age" => 30, "city" => "New York");

//Example 2
$array=["1"=>2,"Aman"=>'david',"2"=>'David'];
```
**Multi-dimensional Arrays**
* Arrays containing one or more arrays as elements.
```Php
$matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];
echo $matrix[1][1];
```
---
## 📘 Array Method
**Count**
```Php
$food=["Banana","1"=>"Orange","true"=>"Apple"];
echo count($food);  //Output 3
//use
$len=count($food)
for($i=0;$i<$len;$i++){
echo $food[$i]."<br>";
}

// Cout inner array
$food = ["Banana",
 "1" => "Orange",
  "true" => array('Orange', 'Banana', 'Graphs'),
  "veggi"=>array('carrot','pea','tea')];
echo count($food,1);// output 10 Give all the totall array include inner rray also adding 1 parameter 
```
***
**Size of**
```Php
$food=["Banana","1"=>"Orange","true"=>"Apple"];
echo Sizeof($food);  //Output 3

//inner array count
$food = ["Banana",
 "1" => "Orange",
  "true" => array('Orange', 'Banana', 'Graphs'),
  "veggi"=>array('carrot','pea','tea')];
echo Sizeof($food,1);// output 10 Give all the totall array include inner rray also adding 1 parameter 
```
***
**array_count_values**
* In PHP, the array_count_values function is used to count the occurrences of each unique value in an array. It takes an array as input and returns an associative array where the keys are the unique values from the input array, and the values are the counts of each unique value.
```Php
$fruits = ['apple', 'banana', 'orange', 'apple', 'banana', 'apple'];
echo array_count_values($fruits); //output Error Array to string conversion Return Array

echo "<pre>";
print_r(array_count_values($fruits));
echo "<pre/>"; 
//output Array
// (
//     [apple] => 3
//     [banana] => 2
//     [orange] => 1
// )  //Also count how many times values or array repeat
```
***
**in_array**
* in_array is used to check whether a specific value exists in an array.
* It returns true if the value is found, and false otherwise.
```Php
$fruits = ['apple', 'banana', 'orange', 'kiwi'];
if (in_array('banana', $fruits)) {
    echo "Found";
} else {
    echo "Not found";
} // Output Found

```
**in_Search**
* array_search is used to find the key associated with a particular value in an array.
* If the value is found, it returns the corresponding key; otherwise, it returns false.
```Php
$fruits = ['apple', 'banana', 'orange', 'kiwi'];
$key = array_search('banana', $fruits);
if ($key !== false) {
    echo "Found at index: $key";
} else {
    echo "Not found";
} // output Found at index: 1

```
***

**Array_replace & Array_replace_recursive**
![Screenshot (326)](https://github.com/amandavid0032/Web-Development/assets/86879390/9beaadff-94fd-4e9c-88bc-a7554edc879c)
***
**Array_replace**
This function replaces the values of the first array with the values from the given arrays. If a key exists in the first array, its value will be replaced by the corresponding value from the next array. If the key doesn't exist in the first array, it will be created. This function operates in a non-recursive manner, meaning it does not recursively replace elements in nested arrays.
```php
$array1 = array('a', 'b', 'c');
$array2 = array(0 => 'x', 2 => 'y');
$result = array_replace($array1, $array2);
print_r($result); // Output: Array ( [0] => x [1] => b [2] => y )
print_r($array1);//Output:Array ( [0] => a [1] => b [2] => c )
```
***
**Array_replace_recursive**
Work with Mulitdeminsonal
```php
$array1 = array('a', 'b', array('c', 'd'));
$array2 = array(0 => 'x', 2 => array(0 => 'y'));
$result = array_replace_recursive($array1, $array2);
print_r($result); // Output: Array ( [0] => x [1] => b [2] => Array ( [0] => y [1] => d ) )
```
***
**Array_pop**
 Pop refers to the operation of removing the last element from an array or stack and returning it and mutate the array
```php
$my_list = [1, 2, 3, 4, 5];
$popped_element = array_pop($my_list);
echo $popped_element."</br>";   //output:5
print_r($my_list); //output:Array ( [0] => 1 [1] => 2 [2] => 3 [3] => 4 )
```
***
**Array_push**
Push is the operation of adding an element to the end of an array or stack. This operation increases the size of the array or stack by one
```php
$myArray = array(1, 2, 3); // Output:Array ( [0] => 1 [1] => 2 [2] => 3 )
print_r($myArray);
array_push($myArray, 4);
print_r($myArray);  // Output: Array ( [0] => 1 [1] => 2 [2] => 3 [3] => 4 )
```
***
**Array_shift**
This function removes the first element from an array and returns it. The remaining elements in the array are reindexed sequentially, starting from zero
```php
$myArray = array(1, 2, 3, 4, 5);
$shiftedElement = array_shift($myArray);
echo $shiftedElement; // Output: 1
print_r($myArray);    // Output: Array ( [0] => 2 [1] => 3 [2] => 4 [3] => 5 )
```
***
**Array_unshift**
This function adds one or more elements to the beginning of an array. The existing elements shift to higher indices to accommodate the new elements.
```php
$myArray = array(2, 3, 4, 5);
array_unshift($myArray, 1);
print_r($myArray); // Output: Array ( [0] => 1 [1] => 2 [2] => 3 [3] => 4 [4] => 5 )
```
***
**array_merge:** 
This function merges two or more arrays into a single array. It appends the elements of the second array to the first array. If there are duplicate keys, the later value will overwrite the previous one.
```php
$array1 = array('a', 'b', 'c');
$array2 = array('d', 'e', 'f');
$mergedArray = array_merge($array1, $array2);
print_r($mergedArray); // Output: Array ( [0] => a [1] => b [2] => c [3] => d [4] => e [5] => f )
```
***
**array_combine:**
This function creates an array by using one array for keys and another for its corresponding values. Both arrays must have the same number of elements, otherwise, an error will occur.
```php
$keys = array('a', 'b', 'c');
$values = array(1, 2, 3);
$combinedArray = array_combine($keys, $values);
print_r($combinedArray); // Output: Array ( [a] => 1 [b] => 2 [c] => 3 )
```
***
**Array_slice**
In PHP, array_slice is a function used to extract a slice of an array. It returns a portion of the original array, starting from the specified offset and containing the specified length of elements.
mean i want to creat new array from specific value from remaning value
`array_slice(array $arrayname, int $offset, ?int $length = null, bool $preserve_keys = false): array`
```php
$array = array('a', 'b', 'c', 'd', 'e');
$slice1 = array_slice($array, 2); // Extract elements from index 2 to the end
print_r($slice1); // Output: Array ( [0] => c [1] => d [2] => e )

$slice2 = array_slice($array, 1, 2); // Extract 2 elements starting from index 1
print_r($slice2); // Output: Array ( [0] => b [1] => c )

$slice3 = array_slice($array, -2, 2); // Extract 2 elements starting from the second-to-last element
print_r($slice3); // Output: Array ( [0] => d [1] => e )
```
***
**Array_splice**
In PHP, array_splice is a function used to remove a portion of an array and replace it with new elements. This function can also be used to insert new elements into an array at a specified position.
```php
$array = ['a', 'b', 'c', 'd', 'e'];
$removed = array_splice($array, 2); // Remove elements starting from index 2 to the end
print_r($array); // Output: Array ( [0] => a [1] => b )

$array = ['a', 'b', 'c', 'd', 'e'];
$removed = array_splice($array, 1, 2); // Remove 2 elements starting from index 1
print_r($array); // Output: Array ( [0] => a [1] => d [2] => e )
print_r($removed); // Output: Array ( [0] => b [1] => c )

$array = ['a', 'b', 'c', 'd', 'e'];
$removed = array_splice($array, 2, 1, ['x', 'y']); // Remove 1 element starting from index 2 and replace with 'x' and 'y'
print_r($array); // Output: Array ( [0] => a [1] => b [2] => x [3] => y [4] => d [5] => e )
print_r($removed); // Output: Array ( [0] => c )
```
***
**Array Key Function**
**Array_key:**
This function returns all the keys of an array or the subset of keys of an array that match a specified value.
```php
$array = array('aman' => "Aman", 'david' => "david", 'hello' => 3, 'hi' => 2);
$keys = array_keys($array);
print_r($keys); // Output: Array ( [0] => aman [1] => david [2] => hello [3] => hi )
```
***
**Array_key_exist**
This function checks if a specified key exists in an array.
```php
$array = array('aman' => "Aman", 'david' => "david", 'hello' => 3, 'hi' => 2);

if (key_exists('hi', $array)) {
    echo 'Key "hi" exists';
} else {
    echo 'Key "hi" does not exist';
}
```
***
**key_exist** work as same of `array_key_exist`
***
**Array Diff & udiff**
**array_diff:** the difference between arrays, i.e., it returns an array containing all the values from array1 that are not present in any of the other arrays. and return how don't present in array 2 
```php
$array1 = array('aman', 'david', 'hi');
$array2 = array('aman', 'hello', 'hi');
$difference = array_diff($array1, $array2);
print_r($difference); // Output: Array ( [1] => david )
```
***
**udiff** user define function its need 3 parameter 2 array for compare and 1 function
***
**array_values:**
 This function returns all the values of an array and re-indexes the array numerically, starting from zero. It effectively removes the keys and preserves only the values.
```php
$array = array('a' => "AMAN", 'b' => "David", 'c' => "AAAA");
$values = array_values($array);
print_r($values); // Output:Array ( [0] => AMAN [1] => David [2] => AAAA )
```
***
**array_unique:** This function removes duplicate values from an array, preserving the keys of the original array.
```php
$array = array('a' => "AMAN", 'b' => "David", 'c' => "AAAA",'d'=>"AMAN",'E'=>"AMAN");
$values = array_unique($array);
print_r($values); // Output:Array ( [a] => AMAN [b] => David [c] => AAAA )
```

---

## 📘 Htmlentities
* PHP function used for converting special characters to their HTML entities. This is particularly useful when you want to display user-input data on a 
  webpage and avoid potential security And Protect From the hacker they can't use Sql injection on this such as Cross-Site Scripting (XSS).By converting special characters to their HTML entities<br/>
**ENT_COMPAT**
* This flag is the default and stands for compatibility.
* It converts double-quotes and leaves single-quotes unconverted.
```Php
$link = '<a href="http://localhost/pratice/pratice.php"></a>';
echo htmlentities($link, ENT_COMPAT);
// Output &lt;a href="http://localhost/pratice/pratice.php"&gt;&lt;/a&gt;
```
**ENT_QUOTES**
* This flag converts both double-quotes and single-quotes.
```Php
$link = '<a href="http://localhost/pratice/pratice.php"></a>';
echo htmlentities($link, ENT_QUOTES);
//Output &lt;a href=&quot;http://localhost/pratice/pratice.php&quot;&gt;&lt;/a&gt;
```
**ENT_NOQUOTES**
* This flag leaves both single-quotes and double-quotes unconverted.
```Php
$link = '<a href="http://localhost/pratice/pratice.php"></a>';
echo htmlentities($link, ENT_NOQUOTES);
//output <a href="http://localhost/pratice/pratice.php"></a>

```
**html_entity_decode**
* html_entity_decode function is used to convert HTML entities back into their corresponding characters. 
```Php

$str = "&lt;a href=&quot;http://localhost/pratice/pratice.php&quot;&gt;&lt;/a&gt";
echo html_entity_decode($str, ENT_COMPAT); // Will only convert double quotes
echo "<br>"; //Output <a href="http://localhost/pratice/pratice.php">
echo html_entity_decode($str, ENT_QUOTES); // Converts double and single quotes
echo "<br>";//Output <a href="http://localhost/pratice/pratice.php">
echo html_entity_decode($str, ENT_NOQUOTES); // Does not convert any quotes
echo"<br>";//Output <a href=&quot;http://localhost/pratice/pratice.php&quot;>
```
---
## 📘 Md5 & Sha1
**Md5**
1.MD5 is a widely used cryptographic hash function that produces a 128-bit (16-byte) hash value, typically expressed as a 32-character hexadecimal number.

2.It takes an input (or message) and produces a fixed-size output hash value.

3.Its save from hacker because it's value is in the hash value and don't read 

4.It's Default vaule is false in 32 hex number
 ![Screenshot (322)](https://github.com/amandavid0032/Web-Development/assets/86879390/264d9d73-dcda-4af0-9941-780c6278dfa1)
***
```php
$input = "Hello World";
$md5_hash = md5($input);
echo "MD5 hash of '$input': $md5_hash";  //output MD5 hash of 'Hello World': b10a8db164e0754105b7a99be72e3fe5

```
***
**SHA 1**
1. SHA-1 is a cryptographic hash function that produces a 160-bit (20-byte) hash value, typically expressed as a 40-character hexadecimal number.

2.Like MD5, it takes an input and produces a fixed-size output hash value.

3.SHA-1 was widely used, but it is now considered to be vulnerable to collision attacks and is no longer recommended for cryptographic purposes.
![Screenshot (323)](https://github.com/amandavid0032/Web-Development/assets/86879390/4813c499-4f8c-4dc3-a89c-0cf789daef37)
```php
$input = "Hello World";
$sha1_hash = sha1($input);
echo "SHA-1 hash of '$input': $sha1_hash"; //output SHA-1 hash of 'Hello World': 0a4d55a8d778e5022fab701977c5d840bbc486d0
```
---
## 📘 More Function like Md5 
**Convert_uuencode**  
same work as md5 but there is one diffrence in this it has no limit means md5 give hash value in 32 bite but its has  more then 32 bite
** Convert_uuencode**
```php
$original_data = 'Aman';
$encoded_data = convert_uuencode($original_data);
echo "Encoded data: $encoded_data";  //output-Encoded data: %06UA;BX` `
```
***
**Convert_uudecode**
```php
$encoded_data = '0=&5S=`8`';
$decoded_data = convert_uudecode($encoded_data);
echo "Decoded data: $decoded_data";

```
***
**bin2hex:**
This function converts binary data to its hexadecimal representation. In other words, it takes a sequence of binary digits (0s and 1s) and converts them into their equivalent hexadecimal digits (0-9, A-F). 

Syntax
`echo bin2hex("My first PHP script!");`

`echo hexbin2('$value');`
***
**Chr:** BASIC, "Chr" typically stands for "character." often used as a function or command to convert a numeric ASCII or Unicode value into its corresponding character.and it's convert each character into numeric 
![ASCII-Code](https://github.com/amandavid0032/Web-Development/assets/86879390/e2d4f55a-512d-49fd-8817-dde66ee5eb84)
***
`$a=chr(97);

echo $a; //output a`
***
**Ord :** the ord() function returns the Unicode code point for a given character. So ord('A') would return 65, the Unicode code point for the character "A."
`$a=ord("Aman");

echo $a; //output 65`

---
## 📘 Date & Time Function
![Screenshot (324)](https://github.com/amandavid0032/Web-Development/assets/86879390/4aca8a9d-bc62-46b2-86d0-58efd81cfbad)
```php
$date = date("Y-m-d H:i:s"); // Retrieves current date and time in the format "YYYY-MM-DD HH:MM:SS"
echo $date;
```
***
![Screenshot (325)](https://github.com/amandavid0032/Web-Development/assets/86879390/e2c045ec-840d-42fa-8ec2-fe3993ce9816)
***
---
## 📘 
