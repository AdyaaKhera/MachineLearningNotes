# C++

## Input and Output
- All c++ statements end with a semi colon
```C++
#include <iostream> //header file library that helps us with input and output
using namespace std; //we can use names for objects and variables from the standard library
int main() { //main function that returns an integer - 0
  cout << "Hello World!"; //prints hello world
  return 0; }
```
- If we don't use the `namespace std` we can just say `std::cout` while using `cout` or other similar objects
- While using these objects we need to declare that they are part of the standard `std` library
- - For inputs, we can use `cin` by using the `>>` operator
  ```C++
  int x;
  cout << "enter number: ";
  cin >> x;
- `cin` considers a space as a terminating character, which means that it can only store a single word even if more than one words are entered
- Both `cin` and `cout` belong to the <iostream> library, which is short for **standard input / output streams**.
  
## Data types
- Variables should be created in the form: `type name = value`

| Data Type | Size         | Description                                                                 |
|-----------|--------------|-----------------------------------------------------------------------------|
| `bool`    | 1 byte       | Stores `true` or `false` values.                                           |
| `char`    | 1 byte       | Stores a single character/letter/number, or ASCII values.                  |
| `int`     | 2 or 4 bytes | Stores whole numbers, without decimals.                                    |
| `float`   | 4 bytes      | Stores fractional numbers, containing one or more decimals. Sufficient for storing 6–7 decimal digits. |
| `double`  | 8 bytes      | Stores fractional numbers, containing one or more decimals. Sufficient for storing 15 decimal digits. |
| `string`  | Varies       | Stores a sequence of characters (text).           |

- There are a few ways to inset a new line in C++
```C++
cout << "HI! \n";
cout << "HI!" << "\n";
cout << "Hello" << endl;
```
- `\n` is called an **escape sequence** which moves the cursor to the next line.
- To display variables while printing them we use ``<<``
  ```C++
  int age = 20;
  cout << "you are" << age << "years old!";
- The names used for variables are called identifiers
- We can also create constants
  ```C++
  const int pi = 3.14;
- Constants cannot be assigned a value later. It must be done at the time of declaration.
- The datatype `string` is not built-in so we have to include the `<string>` library everytime we want to use it.
- `auto` is a keyword that lets the compiler firgure out the datatype of a variable. So instead of saying `int x = 5;` we can just say `auto x = 5;`
- `auto` only works when the value is assigned at the time of variable declaration
- once a datatype is assigned to a variable, it is fixed.
  
  ### Strings
- Strings are objects in C++
- Other than using `+`, we can also concatenate strings using `append()` function since it's an object
- the `length()` or `size()` function can be used to find the length of a string
- C++ does not support negative indexing natively
  ```C++
  string myString = "Hello";
  cout << myString[myString.length() - 1];
- We can also use the `at()` function for accessing a character at the particular index
  ```C++
  #include <string>
  string str = "hello";
  cout << str.at(1);
- Since `cin` can only input one word, we use `getline()` function to read a line of text
  ```C++
  cout << "enter variable value";
  getline (cin, variable_name);
- `string` is also an object of the std library
- **C-Style strings** are created using the `char` datatype by creating an array of characters to make a string
  ```C++
  char greeting2[] = "Hello";

## Operators
- `>>=` and `<<=` are shorthand bitwise operators used to shift a bit value to the left or right by a certain number
- Logical Operators are `&&` (and), `||` (or) and `!` (not)

## Math
- C++ has built in `min()` and `max()` functions
- `<cmath>` library can be used for other math functions like `sqrt()`, `round()`, `log()`, etc.

## Conditionals
```C++
if (condition){
  //statement
} elif (other condition) {
} else {
//statement
}
```
- There is also a **short-hand if else**, which is known as the **ternary operator** because it consists of three operands
  ```C++
  variable = (condition) ? expressionTrue : expressionFalse;
- syntax for switch-case statements
  ```C++
  switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block to run if no match is found
  }

## Loops
- `while` loop goes on for as long as a particular condition is `True`
  ```C++
  while (condition) {
    //tasks to execute if condition is True
    counter variable increment or decrement
  }
- the `while` loop has a variant called the `do/while` loop. It executes once by default and then gets executed for as long as the condition of the while loop is true
  ```C++
  do {
  // code block to be executed
  // variable increment or decrement
  }
  while (condition);
- `for` loop goes on for a specific number of times
  ```C++
  for (intitialize variable; condition; increment or decrement) {
    //block to be executed
  }
- the `foreach` loop is a range-based for loop, used to loop through elements in an array (mainly)
  ```C++
  for (type variableName : arrayName) {
  // code block to be executed
  }
  //or we can use foreach with strings since they are also an array of characters
  string word = "Hello";
  for (char c : word) {
    cout << c << "\n";
  }
## Arrays
- we can omit defining the size of the array, the compiler can automate it but it is a good practice to specifiy it
- we can define an array first and add values to it later but that can't happen without specifying the size of the array while defining it
- arrays have a fixed size, i.e., we cannot add or remove new elements
- **vectors** are resizable arrays, i.e., they have a dynamic size and hence we can add or remove elements as we want
- vectors are part of the `<vector>` library
- to get the size of an array we can use `sizeof()` operator
- `sizeof()` returns the size in bytes
- to get the number of elements in an array we have to divide the size of arrays by the size of the first element
  ### Multidimensional arrays
  - a multidimensional array is an array of arrays
  - To declare a multi-dimensional array, define the variable type, specify the name of the array followed by square brackets which specify how many elements the main array has, followed by another set of square brackets which indicates how many elements the sub-arrays have
    ```C++
    datatype arrayname [elements in outer array][elements in inner arrays]
  - each set of square brackets in an arrays adds a dimension to it
  - multidimensional arrays are great for representing lists

## Structures or Structs
- structs are a way to group related variables
- each variable is called a member of the structure
- structs can contain different datatypes
  ```C++
  struct {
    int intvariable;
    str stringvariable;
    float loatvariable;
    structvar; 
  }
- to access a struct member we just say `structvar.variableName`
- we can also use one struct for many variables; just add however many structnames required separated by a comma as the last line of the struct
  ### Named Structs
  - by naming a struct we can create variables with that structure any time
    ```C++
    struct structname {
      //struct contents
    }
  - to declare a variable using that struct we can just say `structname varname;` by using the struct name as a datatype
 
## Enumeration (enum)
- enum is a group of constants
  ```C++
  enum myconsts {
    const1,
    const2,
    const3
  };
- in order to use the enum we need to create an enum variable `enum enum_name var_name = const1;`
- the created variable can then have any of the values present in the enum
- by default, the first value in the enum will have a value of 0, the second wil have 1 and so on
- these default values can be changed where the enum is defined
  ```C++
  enum myconsts {
    const1 = 100,
    const2 = 25,
    const3 = 50
  };
- if we only assign the first constant a value, the next ones will take the preceding values by default

## References
- a reference is an alias for an existing variable
- a reference is creating using `&`
  ```C++
  string something = "something";
  string &alias_something = something;
- once the reference has been made, the reference or the original varible, either can be used as both refer to the same memory location
- references give us the ability to manupulate the data in the computer's memory which can reduce code and improve the performance. This is one of the things in C++ that it is known for

## Memory Address
- we can use the `&` operator to access the memory address of a particular variable
- the memory address is in hexadecimal form

## Pointers
- a pointer is a variable that stores the memory address as its value
- a pointer points to a data type of the same type and is created with `*` operator
  ```C++
  string something = "something";
  string* &also_something = something; //this is a pointer
- **the type of pointer has to match the type of the variable**
- when we change the pointer value, it changes the value of the original variable

  ### Dereference
  - a pointer stores the memory address of a variable but we can use `*`, the dereference operator, with a pointer to get the variable value
    ```C++
    string something = "something";
    string* &also_something = something; //this is a pointer
    cout << *also_something; //this is a dereference and this will say "something"

## Memory Management 
- it is the process of controlling how much memory a program uses and how it's used
- it includes creating, using and releasing memory when not in use
- we can use the `new` keyword to create memory space
  ```C++
  int* pointerr = new int;
  *pointerr = 35;
  cout << *pointerr;
- this creates a new space for one integer and assigns that hexadecimal values to `pointerr`
- we dereference the `pointerr` and assign it a value of 35 so when we print the dereference, we get 35
- bascially, we create a space first and then dereference the space to assign the pointer a value
- when we create something with `new` we have to remove it when we're dones
- we can use `delete` keyword to remove `pointerr` by `delete pointerr;`
- if we forget deleting the space after its use the program will keep on using more and more space and a memory leak will happen
- `new` and `delete` can also be used with arrays
- when using with arrays, `new ` and `delete` become `new[]` and `delete[]`
- manual memory management isn't always required but can be useful when full control over the memory is desired

## Functions
- functions in C++ are always declared **with** datatypes
- if a user-defined function is declared after the `main()` function, there will be an error
- functions can be defined after `main()` but need to be declared before `main()`
- parameters are specified **with** their datatypes: `void funcname(string parameter1){}`
- the parameters can also be assigned a default value
- a parameter with a default value is known as an "optional parameter" since the function will work even if we don't pass an arguement
- when the function is not a `void` function, it must contain a `return` statement that returns the datatype that was specified while declaring the function

  ### Pass by reference
  - we can pass a reference a parameter to the function
  - the passed argument then becomes a reference to the assigned value in the parameter
    ```C++
    void changeValue(int &num) {
    num = 50;
    }
    int main() {
      int value = 10;
      changeValue(value);  // Call the function and change the value to 50
      cout << value; 
      return 0;
    }
  - using structs in a function can be useful as it allows us to use a group of variables while only passing the struct variable as an argument

  ### Function overloading
    - allows multipple functions to have the same name as long as their parameters have different datatypes or number of parameters

  ### Lambda functions
    - small anonymous function that can be written directly in the code
    - useful for quick functioning without declaration or definition
    - for using lambda in a function we need the `<functional>` library as we need `std::functional` to specify the datatype op the function
    - syntax: `[capture] (arguments) {statemnts to execute}`
    - the capture clause [] gives lambda the access to variables outside of it so that they can be used
    - references can also be captured
    - lambda functions should be only used when they are required only once

## OOP
- to create a class, we use the `class` keyword, then we use an access specifier and declare the attributes
  ```C++
  class MyClass {
    public: //specifies that the members of the class re accessible from outside the class
      int mynumber;
      str mystring;
  };
- to create an object of `MyClass`, the class name is specified, followed by the object name: `MyClass myobj;`
- to access the class attributes we can use the dot syntax: `myobj.mynumber = 10;`

  ### Class Methods
  - functions that belong to the class are called methods
  - the methods can be defined inside or outside the class
    ```C++
    class MyClass {
      public:
        int firstatr;
        void firstfunc() {
          cout << "I do nothing\n";
        }
    };
  - we can call this method by first creating and object and then calling the function: `myobj.firstfunc();`
  - to define a methode outside the class, we have to declare it in the class
  - for function definition outside the class we use the `::` scope resolution operator (just like when we use `cin` and `cout` directly froms `std` instead of `using namespace std`)
    ```C++
    class myclass {
      public:
        void mymethod();
    };

    void myclass::mymethod() {
      cout << "I also do nothing\n";
    }
    ```
    ### Constructors
    - constructor is a special method that is automatically called when an object is created
    - a constructor has the same name as the class followed b a parenthesis
      ```C++
      class myclass {
        public:
          myclass() { //this is the constructor
            cout << "why would I do anything?\n";
          }
      };
    - the constructor has **no** return type and is usually declared public
    - constructors can also be defined outside the class since they are also methods
    - constructors can also be overloaded

    ### Access Specifiers
    - access specifiers control how the members of a class are accessed
    - there are three access specifiers
    - `public` - members ae accessible from outside the class
    - `private` - members cannot be accessed or viewed from outside the class
    - `protected` - members cannot be accessed from outside but can be accessed in inherited classes
    - by default the attributes are `private`
    - `private` attributes can be accessed by creating get and set methods
    - a `friend` function can be used to access `private` attributes
    - a `friend` function is not a member fo the class,, it is defined outside the class but declared as a friend inside the class: `friend void friend_func_name(class_name class_obj);`
      
  ### Inheritance
  - one class reusing the attributes and methods of another class
  - there's a parent class and a child class with the child class being the one that inherits its properties from the parent class
  - to make a child class `:` is used
    ```C++
    class parent {
      public:
        void message() {
          cout << "I'm the parent class";
        }
    };

    class child : public parent {
      public:
        //child class specific attributes and methods
    };
  - when a class is derived from an already derived class, it is known as multilevel inheritence
  - a child class can also be derived from multiple base classes
  ```C++
  class child : public firstclass, public secondclass {
    public:
      //this class derives its attributes and methods from first and second class
  };
  ```
  - protected attributes and methods can be inherited by child classes

  ### Polymorphism
  - polymorphism is the same attribute / method behaving differently for each child class

    ### Virtual Functions
    - virtual function is the base class function that can be overriden in derived classes
    - without specifying a `virtual` function, the original function from the parent class would be called
    - virtual functions are key to using polymorphism
    - to use virtual functions, just use `virtual` keyword when declaring functions in parent class and `override` after function name in child class (`override` part is optional)
    - the `->` operator is used to access members of a class through a pointer so we can say `pointerr->classfunc();` or we can dereference the pointer and then user the function: `*pointerr.classfunc();`

  ### Templates
  - a function or class that works with different data types
  ```C++
  template <typename T>
  return_type function_name(T parameter) {
    // code
  }
  ```
  - T is a datatype placeholder
  - these templates can be used by: `function_name<typename>(parameter)`
  - just like a function we can create a template for a class and write the methods and other attributes using T

## Files
  - `<fstream` library can be used to work with files
  - both `<iostream>` and `<fstream>` are required
  - `ofstream`, `ifstream` and `fstream` classes are used from the `<fstream>` library to create, write and ride files
  - to write to a file:
  ```C++
  ofstream filenamevar("filename.txt");
  filenamevar << "something I wanna add to the file";
  filenamevar.close();
  ```
  - to read from a file:
  ```C++
  string filetext;
  ifstream filenamevar("filename.txt");
  while (getline(filenamevar, filetext)) {
    cout << filetext;
  }
  filenamevar.close();
  ```

## Date and Time
  - `<ctime>` library can be used to work with dates and times
  - `time_t` is the datatype to store timestamp values and `struct tm` is for datetime structures
  - timestamps represent the moment in time as a single number from the epoch so that it's easier for computers to do the calculations
  - The `time()` function gives us a timestamp representing the current date and time. We can use the `ctime()` function to show the date and time that a timestamp represents
  - The `time()` function writes a timestamp to the memory location given by the parameter, but it also returns the timestamp's value
  - An alternative way to use the `time()` function is to pass in a `NULL` pointer and use the return value instead
  - we can create a timestamp for any date using `mktime()` instead of `time()`
  - The `mktime()` function needs these members to have a value: `tm_year`, `tm_mon`, `tm_mday`, `tm_hour`, `tm_min`, `tm_sec` and `tm_isdst`.
  - setting `tm_isdst` to -1 means we want to use the computer's timezone setting
  - The `ctime()` and `asctime()` functions allow us to display the date but they do not allow us to choose how it is displayed. To choose how a date is displayed we can use the `strftime()` function.
  - `strftime()` formats a date as a C-style string into an array

## Exception Handling
  - `try`, `throw` and `catch` can be used to handle exceptions
  - `try` defines the code that may give an error
  - `throw` triggers an exception
  - `catch` handles the error
    ```C++
    try {
      // Code that may throw an exception
      throw 505;
    }
    catch (int errorCode) {
      cout << "Error occurred: " << errorCode;
    }
  - If you do not know the throw type used in the try block, you can use the "three dots" syntax (...) inside the catch block, which will handle any type of exception: `catch (...) {}`

## Data Structures  
  - the various data structures are a part of C++ STL which stands for the Standard Template Library
    
    ### Vector
    - vectors are resizable arrays
    - they are used to store elements of the same datatype
    - `#include <vector>` needs to be included in the code to use vectors
    - the way to create a vector is `vector<type> vectorname;`
    - we use `{}` to declare the values of the vector
    - we can use indexing to access the elements of the vector, starting from 0
    - the first and last elements of the vector can be accessed using the functions `.front()` and `.back()` from the `<vector>` library
    - we can also use the `.at()` function to access an element at a specified index number
    - it is always safer to use the `.at()` function because it displays an error if a certain index doesn't exist
    - using the `.push_back()` function we can add an element at the end of the vector
    - to remove an element from the back of the vector we can use `.pop_back()`
    - `.size()` function can be used to know the size of an array and `.empty()` function can be used to check if it's empty or not. If the vector is empty it will return `1` else `0`

    ### List
    - we can add or remove elemnts from both ends in a list unlike a vector which only supports add or remove at the end of the vector
    - list does not support random access so we cannot directly jump from one index to a specific index
    - to use this datatype, we have to include the `<list>` header file
    - a list can be created by `list<type> listname;`
    - the elements of a list are declared in `{}`
    - the datatype of the elements of a list cannot be changed after it has been declared
    - indexing **cannot** be used to access elements of a list
    - we can still access first and last elements of the list using `.front()` and `.back()` functions
    - `.push_front()` and `.push_back()` are the functions used to add elements at the front and back and `.pop_front()` and `.pop_back()` are the functions that can be used to remove the elements from front and back

    ### Stack
    - a stack stores elements in a specific order called LIFO (last in first out)
    - elements cannot be accessed by index numbers
    - we can only access the element at the top of the stack
    - the `<stack>` header file needs to be included in order to use stacks
    - to create a stack we use `stack<type> stackname;`
    - we cannot add elements to the stack at the time of the declaration unlike with vectors or list
    - we have to use the `.push()` function everytime to add an element to the top of the stack
    - we can only access the top most element using the `.top()` function
    - the `.pop()` function can be used to remove the top most element from the stack

    ### Queue
    - queues store values in the order called FIFO (first in first out)
    - elements cannot be accessed by index numbers
    - elements are added at the end and removed from the front so only those two elements are accessible at all times
    - `<queue>` header file needs to be included for this data structure and they can be created by using `queue<type> queuename;`
    - elements cannot be added to a queue at the time of declaration

    ### Deque
    - a deque is a double ended queue
    - elements from a deque can be added and removed from both ends
    - elements can be accessed by index numbers
    - to use deque, we have to include the `<deque>` header file and a deque can be created by `deque<type> dequename;`
    - elements can be added in a deque at the time of declaration

    ### Sets
    - a set is a data structure of unique elements
    - they are sorted automatically in ascending order
    - elements can be added or removed but the values of an existing element cannot be changed
    - cannot be accessed using the index numbers because the order is determined by automatic sorting
    - the `<set>` header file is required to create a set
    - elements can be added in a set at the time of declaration
    - if we want to change the sort to descending order we can do by during the time of the set declaration by using `set<int, greater<type>> setname = {};`
    - the specified type in `greater` must match the type of the set
    - to add elements to a set we can use the `.insert()` function and to remove an elements, we can use the `.erase()`
    - to remove all elements from the set we can use `.clear()`

    ### Map
    - a map is just like a dictionary, it stores values in the form of key/value pairs
    - elements are accessible by keys and not indices
    - each key is unique
    - the elements are automatically sorted in ascending order by the keys
    - to create a map, we have to include the `<map>` header and use `map<keytype, valuetype> mapname;`
    - the elements of a map can be added at the time of map declaration like `map<string, string> mymap = {{"firstKey","firstvallue"},{"secondkey","secondvalue"}};`
    - we can use `[]` or `.insert()` to add new values to the map
    - `.erase()` can be used to remove a value and `.clear()` can be used to remove all values from the map
    - You can loop through a map with the for-each loop
    - we should use the auto keyword to automatically determine the correct data type for each key-value pair
    - Since map elements consist of both keys and values, we have to include `.first` to access the keys, and `.second` to access values in the loop.
   
    ### Iterators
    - to iterate through a vector, we first have to create a vector iterator, `vector<string>::iterator it;`
    - after the iterator has been created we loop through the vector with the iterator, `for (it = vectorname.begin(); it != vectorname.end(); ++it) {}`
    - the type of iterator must match the type of data structure it refers to
    - iterators are like pointers and instead ofreturning values, they refer to a specific position
    - when we just have to access the elements from these data structures, it's easier to use the for-each loop but when we have to modify the elements using iteration, we should use iterators
    - to iterate in reverse order we can use `rbegin()` and `rend()`
    - instead of creating an iterator first by specifying its type we can just use `auto` in for loop

    ### Algorithms
    - algorithms are used to solve problems by sorting, searching and manipulating data structures
    - we can include the `<algorithm>` library to use some of these functions
    - the `sort()` function takes in two iterators: a start and an end as its parameters. By default, they are sorted in ascending order
    - to use the reverse order, we can use `rbegin()` and `rend()` as the parameters for `sort()`
    - `find()` function can be used to search for specific elements. It takes three parameters: start iterator, end iterator and value where the value represents the value to search for
    - To search for the first element that is greater than a specific value, we can use the `upper_bound()` function instead of `find()`
    - `upper_bound()` is typically used on sorted data structures so we use the `sort()` function before using `upper_bound()`
    - to find the smallest element, we use `min_element()` and to find the largest, we use `max_element()`. We don't have to sort beforehand when using these
    - to fill all elements in a vector with a value, we can use `fill()` function like `fill(vectorname.begin(), vectorname.end(), value_to_fill_the_vector_with);`

## Namespaces
- a namespace is a way to group related code together under a name
- a namespace is like a folder and it can avoid naming conflicts in the program as it keeps growing
- if we don't want to keep referring to the namespace name while using its variable we can just add `using namespace namespacename;` in the code however its better to use the variables from a namespace as `namespacename::variablename`
