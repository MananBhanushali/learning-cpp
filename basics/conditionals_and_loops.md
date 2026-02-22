# Conditional Statements and Loops in C++

## If-else Conditional
The syntax for if-else is as follows
```cpp
if (condition) {
  // code
} 
else {
  // code
}
```
For Ex) You are given a number, you need to print “YES” if it’s divisible by 9 otherwise “NO”.

```cpp
#include<iostream>
using namespace std;

int main() {
  int number;
  cin >> number;
  if (number % 9 == 0) {
    cout << "YES" << "\n";
  } else {
    cout << "NO" << "\n";
  }
  return 0;
}
```

**Using multiple if-else statements**

```cpp
#include<iostream>
using namespace std;

int main() {
  char ch;
  cin >> ch;
  if (ch == 'A') {
    cout << "Yes, it matches" << "\n";
  } else if (ch == 'Z') {
    cout << "Yes, it matches" << "\n";
  } else {
    cout << "No, it doesn't match" << "\n";
  }
  return 0;
}
```

***Using logical operators with if-else***

```cpp
#include<iostream>
using namespace std;

int main() {
  char ch;
  cin >> ch;
  if (ch == 'A' || ch == 'Z') {
    cout << "Yes, it matches" << "\n";
  } else {
    cout << "No, it doesn't match" << "\n";
  }
  return 0;
}
```

## For Loop

**Syntax for a For Loop in C++ is:**
```cpp
for ( initialization; condition; increment/decrement ) {
    // code
}
```

For Ex)
```cpp
#include <iostream>
using namespace std;

int main() {
  for (int i = 0; i < 10; i++) { //For loop used to print numbers from 0 to 9
    cout << i << " ";
  }
  cout << endl;
}
```

## While Loop
While loop is known as entry controlled loop because the test condition is checked before the entry of the loop.

```cpp
while ( condition ){
    // code;
}
```

```cpp
#include<iostream>
using namespace std;

void while_loop() {
  int i = 1, sum = 0;
  while (i <= 5) {
    sum += i;
    i += 1;
  }
  cout << "The sum of first 5 natural number is " << sum;
}
int main() {
  while_loop();
  return 0;
}
// Output: The sum of first 5 natural number is 15
```

### do-while loop:
The do-while loop is similar to the while loop. But the difference is do-while loop is an exit-controlled loop. **The test condition is checked at the end of the looping statement.**

**This means that the body of the loop is executed at least once, even when the condition evaluates false during the 1st iteration.**

```cpp
do {
    // code
} while ( condition );
```

```cpp
#include<iostream>
using namespace std;

void dowhile_loop() {
  int input;
  do {
    cout << "Hello World" << '\n';
    cout << "enter -1 to exit or any other key to "
         << "see this message again" << '\n';
    cin >> input;
  } while (input != -1);
}
int main() {
  dowhile_loop();
  return 0;
}
```

## Switch Case Statement

Switch case is an alternative when you need to compare an expression to a constant value and don’t want to use multiple if-else statements.

```cpp
switch (expression) { 
    case value1: // code break; 
    case value2: // code break; 
    case value3: // code break; 
}
```

**Properties of switch case:**
The expression within the switch statement should return a constant value otherwise it would return an error.  
When no case is matched, one can create a default case to execute a code block.  
A break statement is used in a switch case to break out of the case block and execute the lines that follow the switch-case statement.
Note:  

>[!IMPORTANT]
**When a break statement is missing from a case block and that case matches, it would execute every case after that case.**

```cpp
#include<iostream>
using namespace std;

int main() {
  int x = 2;
  switch (x) {
  case 1:
    cout << "Choice is 1"<<”\n”;
    break;
  case 2:
    cout << "Choice is 2"<<”\n”;
    break;
  case 3:
    cout << "Choice is 3"<<”\n”;
    break;
  default:
    cout << "Choice other than 1, 2 and 3"<<”\n”;
    break;
  }
}
```

## break Statement
A break statement is a jump statement that immediately terminates the execution of a loop. Control is transferred to the statement that follows the loop, resuming normal execution.

### Break statement in for loop
```cpp
#include<iostream>
using namespace std;
void break_statement() {
  for (int i = 1; i <= 10; ++i) {
    if (i == 5) {
      break;
    }
    cout << i << " ";
  }
}
int main() {
  break_statement();
  return 0;
}
// Output: 1 2 3 4
```

Explanation:  
The for loop is supposed to run from 1 to 10.
When i == 5, the break statement executes and terminates the loop.
Only numbers 1 to 4 are printed.

### Break Statement in while loop:
```cpp
#include<iostream>
using namespace std;
void break_statement() {
  int i = 10;
  while (i >= 1) {
    if (i == 6) {
      break;
    }
    cout << i << " ";
    --i;
  }
}
int main() {
  break_statement();
  return 0;
}
Output: 10 9 8 7
```

Explanation:  
The while loop starts from 10 and decrements down to 1.
When i == 6, the break statement executes and the loop stops.
Only numbers 10, 9, 8, and 7 are printed.

### Break Statement in Nested loop:
```cpp
#include<iostream>
using namespace std;
void break_statement() {
  cout << "The value of i and j are:" << '\n';
  for (int i = 0; i <= 5; ++i) {
    for (int j = 0; j <= 5; ++j) {
      if (i + j >= 3) break;
      cout << "i = " << i << ", j = " << j << '\n';
    }
  }
}
int main() {
  break_statement();
  return 0;
}
Output:
The value of i and j are:
i = 0, j = 0
i = 0, j = 1
i = 0, j = 2
i = 1, j = 0
i = 1, j = 1
i = 2, j = 0
```

Explanation:  
The outer loop runs from i = 0 to 5.
The inner loop runs from j = 0 to 5, but if i + j ≥ 3, the inner loop terminates due to the break.
The outer loop continues unaffected.

>[!NOTE]
**If a break statement is used in a nested loop, it terminates only the loop in which it is placed. The outer loop continues execution normally.**

## continue statement
The continue statement works quite similarly to the break statement. **Instead of terminating the loop (break statement), the continue statement forces the loop to continue or execute the next iteration.** When the continue statement is executed in the loop, the code inside the loop following the continue statement will be skipped and the next iteration of the loop will begin.

### Continue statement in a single loop
Problem Statement: print numbers from 1 to 10 except 5 using the continue statement in c++

```cpp
#include <iostream>
using namespace std;

void continue_statement() {
  for (int i = 1; i <= 10; ++i) {
    if (i == 5) {
      continue;
    }
    cout << i << " ";
  }
}

int main() {
  continue_statement();
  return 0;
}
```

Explanation:- In the above program, the loop will iterate 10 times but, if i reach 6, then the control is transferred to for loop, because of the continue statement.

### Continue statement in nested loop
```cpp
#include<iostream>

using namespace std;
void continue_statement() {
  cout << "The value of i and j are:" << '\n';
  for (int i = 1; i <= 3; ++i) {
    for (int j = 1; j <= 3; ++j) {
      if (i == j) continue;
      cout << "i = " << i << ", " << "j = " << j << '\n';
    }
  }
}
int main() {
  continue_statement();
  return 0;
}
```

Explanation:-
In the above program, when the values of i and j are equal the code inside the loop following the continue statement is skipped and starts the next iteration.

## goto statement:
The goto statement is a control statement that is used to transfer the control from one place to another place without any condition in a program.

```cpp
#include<iostream>
using namespace std;

void goto_statement() {
  cout << "ONE" << '\n';
  goto label;
  cout << "TWO" << '\n';
  cout << "THREE" << '\n';
  label:
    cout << "FOUR" << '\n';
}
int main() {
  goto_statement();
  return 0;
}
/*
Output:-
ONE
FOUR
*/
```

Explanation: In the above program, the first cout statement(ONE) has been executed and after that line goto statement tells the compiler to go to the statement marked as a label in this way control is transferred label statement.