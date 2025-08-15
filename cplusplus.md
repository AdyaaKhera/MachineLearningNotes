# C++
## Basics
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
- There are a few ways to inset a new line in C++
```C++
cout << "HI! \n";
cout << "HI!" << "\n";
cout << "Hello" << endl;
```
- `\n` is called an **escape sequence** which moves the cursor to the next line.
- Variables should be created in the form: `type name = value`

| Data Type | Description |
|-----------|-------------|
| `int`     | Stores integers (whole numbers), without decimals, such as `123` or `-123`. |
| `double`  | Stores floating-point numbers, with decimals, such as `19.99` or `-19.99`. |
| `char`    | Stores single characters, such as `'a'` or `'B'`. Char values are surrounded by single quotes. |
| `string`  | Stores text, such as `"Hello World"`. String values are surrounded by double quotes. |
| `bool`    | Stores values with two states: `true` or `false`. |
- To display variables while printing them we use ``<<``
  ```C++
  int age = 20;
  cout << "you are" << age << "years old!";
-

