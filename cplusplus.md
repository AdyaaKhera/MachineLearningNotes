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
- `\n` is called an **escape sequence** which forces the cursor to change its position
<table>
  <tr><th>Data Type</th><th>Description</th></tr>
  <tr><td><code>int</code></td><td>Stores integers (whole numbers), without decimals, such as <code>123</code> or <code>-123</code>.</td></tr>
  <tr><td><code>double</code></td><td>Stores floating-point numbers, with decimals, such as <code>19.99</code> or <code>-19.99</code>.</td></tr>
  <tr><td><code>char</code></td><td>Stores single characters, such as <code>'a'</code> or <code>'B'</code>. Char values are surrounded by single quotes.</td></tr>
  <tr><td><code>string</code></td><td>Stores text, such as <code>"Hello World"</code>. String values are surrounded by double quotes.</td></tr>
  <tr><td><code>bool</code></td><td>Stores values with two states: <code>true</code> or <code>false</code>.</td></tr>
</table>
- Variables should be created in the form `type name = value`

