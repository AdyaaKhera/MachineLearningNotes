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
