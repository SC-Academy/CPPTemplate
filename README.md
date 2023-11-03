## Function and Class Template Example in C++

In this example the function template mySwap() can be used to swap two values of any type. The template parameter T represents the type of the values to be swapped. When the function is instantiated, the compiler will generate a specific version of the function for the given data type.

Class templates allow us to write a single class that can be used with different data types. This is done in a similar way to function templates, but instead of using template parameters for the function parameters, we use them for the class members.

In this example, the class template Pair can be used to represent a pair of values of any type. The template parameters T1 and T2 represent the types of the two values in the pair. When the class is instantiated, the compiler will generate a specific version of the class for the given data types.

The main() function in the example demonstrates how to use the function template mySwap() and the class template Pair with different data types.

### Code 

```
#include <iostream>
using namespace std;

// A function template that swaps two values of any type
template <typename T>
void mySwap(T& a, T& b) {
 T temp = a;
 a = b;
 b = temp;
}

// A class template that represents a pair of values of any type
template <typename T1, typename T2>
class Pair {
 private:
  T1 first; // The first value
  T2 second; // The second value
 public:
  // A constructor that initializes the pair with given values
  Pair(T1 f, T2 s) {
   first = f;
   second = s;
  }

  // A method that returns the first value
  T1 getFirst() {
   return first;
  }

  // A method that returns the second value
  T2 getSecond() {
   return second;
  }

  // A method that prints the pair
  void print() {
   cout << "(" << first << ", " << second << ")" << endl;
  }
};

int main() {
 // Using the function template with different types of arguments
 int x = 10, y = 20;
 cout << "Before swapping: x = " << x << ", y = " << y << endl;
 mySwap<int>(x, y); // Explicitly specifying the type parameter as int
 cout << "After swapping: x = " << x << ", y = " << y << endl;

 double a = 3.14, b = 2.71;
 cout << "Before swapping: a = " << a << ", b = " << b << endl;
 mySwap(a, b); // Implicitly deducing the type parameter as double
 cout << "After swapping: a = " << a << ", b = " << b << endl;

 char c = 'A', d = 'B';
 cout << "Before swapping: c = " << c << ", d = " << d << endl;
 mySwap(c, d); // Implicitly deducing the type parameter as char
 cout << "After swapping: c = " << c << ", d = " << d << endl;

 // Using the class template with different types of arguments
 Pair<int, int> p1(1, 2); // Creating an object of Pair<int, int>
 p1.print(); // Printing the pair

 Pair<string, double> p2("Hello", 4.5); // Creating an object of Pair<string, double>
 p2.print(); // Printing the pair

 Pair<char, bool> p3('X', true); // Creating an object of Pair<char, bool>
 p3.print(); // Printing the pair

 return 0;
}
```
### Usage

To compile and run the program, simply execute the following commands: </br>
 `g++ main.cpp -o main ` </br>
`./main`

### Output

The program will print the following output to the console:

Before swapping: x = 10, y = 20   </br>
After swapping: x = 20, y = 10   	</br>
Before swapping: a = 3.14, b = 2.71	  </br>
After swapping: a = 2.71, b = 3.14	  </br>
Before swapping: c = A, d = B		  </br>
After swapping: c = B, d = A		  </br>
(1, 2)  </br>
(Hello, 4.5)  </br>
(X, true)

## License
This project is licensed under the MIT License. For more information, please see the LICENSE file.


