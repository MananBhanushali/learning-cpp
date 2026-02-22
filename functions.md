# Functions in C++

Functions can be simply considered as a machine, which takes some input, and gives us some output according to the function definition.

```cpp
return_type function_name(arg1 , arg2 , …){ 
    // code
    return statement 
} 
```

For Ex)
```cpp
int product(int x, int y) { // function declaration , and passing parameters 
    return x*y; 
} 

int main() { 
    int a; 
    cin >> a; 
    int b; 
    cin >> b; 
    int ans = product(a, b); // return value from the function is stored in ans variable
} 
```

### Types of arguments:  

**Pass by value:** In this, the value of the actual parameters is copied to the formal parameters and the actual and formal parameters point to different memory locations. So, even if we change something in the parameters, there is no change in the actual value. **Changes inside the function don’t affect the original variable.**   
**Pass by reference:** In this, no copy is created, and the actual and formal parameters point to the same memory locations. so if a change is made in formal parameters then, actual parameters will also change. **Changes inside the function affect the original.**

## Function Overloading
C++ allows us to use the same function in the same program but with different numbers and types of arguments. **It is a feature of object-oriented programming where two or more functions can have the same name but different parameters.**

Conditions required for a function to be known as an overloaded function are :  
Different types of parameter, or  
Different number of parameter  
Advantages of function overloading are:

Example: To find the area of circle, triangle, square and rectangle using function overloading. Explanation: Here we will code a program which will use the overloaded function (area) to find the solution of the given example

```cpp
#include<iostream>
using namespace std;
const float pi=3.14;

float area(float n,float b,float h) {
    float ar;
    ar=n*b*h;
    return ar;
}

float area(float r) {
    float ar;
    ar=pi*r*r; 
    return ar;
}

float area(float l,float b) {
    float ar;
    ar=l*b;
    return ar;
}

int main() {
    float b,h,r,l;
    float show;
 
    show=area(0.5,4,5);
    cout<<"The area of the Triangle is "<<show<<endl;
    show=area(12);
    cout<<"The area of the Circle is "<<show<<endl;
    show=area(7,9);
    cout<<"The area of the Rectangle is "<<show<<endl;
    
    return 0;
}
/*
Output:
The area of the Triangle is 10
The area of the Circle is 452.16
The area of the Rectangle is 63
*/
```