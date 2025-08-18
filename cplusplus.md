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
