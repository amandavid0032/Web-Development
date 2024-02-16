## 📔 OOPS With PHP

## 📘 Developer Responsibility
* Write good code so everyone can read and understand easily.
* the harder is to understand code and to reason about the code the more difficult it will be to add new features add to more the functionality to the * * * application. Hence it is called bad code.
* An important part of web-development is actually handle the errors. because its very common that errors happen in web-application.
* To test APi use Network tab with various Throttling options fast/slow/offline
---
## 📘 Some important query
1. Connection
	$con= new mysqli(Server name, User Name, Password , Database name);

2. Run Sql Query
	$con->query(Sql Query);

3. Close Connection 
	$con->close();

 **MYSQLi Featch Function** 
 
this function is use to show the data from the the database 

Fetch Query

  $result=$con->query(Sql Query) 																|
	 
	 1. `$result->mysqli_fetch_assco();`    // Show All the record but convert the data into associative array with there value and show the data write the key of the data 
	 2. `$result->mysqli_fetch_array();`    // Show All the record but give bhot type of data associative array and index array we  give the type what type of data we want in this  
	 3. `$result->mysqli_fetch_row();`      //Show all the recrod but convert the data into index array and two show the array write the index number  
	 4. `$result->mysqli_fetch_all();`      //Show all the data in one array and make a multidemensional array  and it's is use with for each loop
	 5. `$result->mysqli_fetch_field();`    //give the deatils about the field  just
   6. `$result->mysqli_affected_row()`    // show how much data in table like there are 6 row in table it's return 6   
   7. `$result->mysqli_num_rows();`       // retunr the number of the rowsin result set    
 
  ```php
$result=mysqli_query($conn.$sql)
while($row=mysqli_fetch_assoc){ write any method to show the data
echo 
}
```
***
**Errors**

	 a. $con->connect_error();            //what error in the query 
	 b. $con->connect_errno();            // return error no each and every error has unique no 
	 c. $con->error();                    //show the error 
	 d. $con->error_list();              // give the list of error in array 

 ```php
$result = $con->query($sql);
if (!$result) {
    $errors = $con->error_list();
    foreach ($errors as $error) {
        echo "Error: " . $error['error'] . "<br>";
    }
}
```
***

