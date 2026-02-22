# Arrays and Strings in C++

## Array
An array is a linear data structure in which we store data and perform any operation, we can access data in an array with the help of its index values. 

In other words, **an array is a collection of similar types of elements (Homogeneous elements) that have contiguous memory locations i.e One after another.**

The array of length n can be indexed by the integers from 0 to n-1.

Arrays can store numbers, strings, boolean values, characters, objects, etc. But once you define the type of values that your array will store, all its elements must be of that same type.

**Creating an array :**  
Assign it to a variable (Name of an array).  
Define the type of elements that it will store (integer, string, boolean).   
Define its size (the maximum number of elements it will store).  

E.g: int myarray [8]; 

Int     => Datatype.  
myArray => Name of an array.  
[8]     => Size of an array.  

## Strings
Strings are like a series of characters stored in a specific order.  
Each character in a string is assigned an index, starting from 0.  

### String Functions

**length():** returns the length of the string  
**find():** returns the starting index of the character  
**substr():** accepts starting index as parameter and returns substring 
starting from that index to end.  
**at():** accepts index as a parameter and returns character present at that index ( Similar to s[idx] )  
**append():** accepts another string object, index, length, number of characters to copy as a parameter and pushes the defined parameter to the end of the string.  
```cpp
string s="takeuforward";
cout<<s.length(); // prints 12
cout<<s.find('a'); // prints 1
cout<<s.substr(3); // prints euforward
cout<<s.at(2); // prints k
cout<<s.append("123"); // prints takeuforward123
```

**getline():** accepts istream object and string object as parameter and extracts characters from istream object and stores them into a string object until a delimiter character is found.
```  cpp
string s;
cout<<"Enter the string: ";
getline(cin,s);
cout<<"\ns holds: "<<s; // prints the complete input line 
```

**compare():** accepts string object as a parameter and returns 0 or another integer if string matches or not respectively.
```cpp
string s="takeuforward";
string str="striver";
s.compare(str) ? cout<<"doesn't match" : cout<<"matches"; // returns doesn't match
```

**clear():** clears the string and makes it an empty string
```cpp
string s="takeuforward";
s.clear();
cout<<s; // prints “”
```

**front():** can be used to access the first character of the string.
**back():** can be used to access the last character of the string.
```cpp
string s="takeuforward";
cout<<s.front(); // prints t
cout<<s.back(); // prints d
```
