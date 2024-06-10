# C++ Tutorial
My way of learning C++  
...once again...  

Tutorial i'm learning from: [C++ for Java Programmers by Mary Elaine Califf](https://www.youtube.com/watch?v=ZzaPdXTrSb8&)  
I already *\*cough\** know *\*cough\** Java, so this tutorial will (mostly) show the differences of C++ compared to Java

# Hello World
```c++  
#include <iostream>
// using namespace std;

int main() {
    std::cout << "Hello world!" << std::endl;
    return 0;
}
```

# Input/Output  
Standard input stream - **cin**  
Standard output stream - **cout**

```c++
std::cout << "Enter your age: ";

int age;
std::cin >> age;
std::cout << "Your age is: " << age << std::endl;

return 0;
```

# Primitive types
| Modifier | Minimum Size |
|-|-|
| short | 16 bits |
| long | 32 bits |
| long long | 64 bits |

| Integer Sign | Min | Max |
|-|-|-|
| Signed | -2_147_483_648 | 2_147_483_647 |
| Unsigned | 0 | 4_294_967_295 |

0 is ***false***  
Everything other is ***true***

Keyword for constant is **const** rather than final  
Value has to be assigned to constant when declared, it cannot be changed afterwards  

# Functions
Functions can exist outside classes  

Order matters - you have to declare the function before using it  
By typing `#include <iostream>` you are putting all functions of *iostream* to your program  

### Example
#### Error
We tried to run *calculate()* before it was declared  
```c++
#include <iostream>

int main() {
    int result = calculate(5);
    std::cout << result << std::endl;
}

double calculate(double number) {
    return number * 2;
}
```

#### Fix #1
We moved *calculate()* before *main()*
```c++
#include <iostream>

double calculate(double number) {
    return number * 2;
}

int main() {
    int result = calculate(5);
    std::cout << result << std::endl;
}
```

#### Fix #2 - function prototype
It is recommended to use this way
```c++
#include <iostream>

double calculate(double number);

int main() {
    int result = calculate(5);
    std::cout << result << std::endl;
}

double calculate(double number) {
    return number * 2;
}
```

# Parameters 
## Pass by value
Default way, 
