# Day 11: Array 

Table of Content
- Array
- Length/ Size in Array
- Array Functions 
- Basic Array Operations
- Find Element in Array
	- Min - Max
	- Find 2nd last element - 2nd Max 
 - Char Array Practice Questions
	- Reverse Char Array (String)
	- Check If String is palindrome
- Filter Array 
- Push/Insert Element in Array
- PoP/Remove/Delete Element in Array

.


## Array
An array is a **collection of items of same data type stored at contiguous memory locations.**

```c++
int score[5] = { 16, 2, 77, 40, 121 };  
```

```c++
int arr[] = {1,2,3,4,5};
	// let arr = 100 + (3*4) = 112 
	cout << *(arr+3) << endl;
	cout << arr[3] << endl;
```

.

When an **initialization** of values is provided for an array, C++ allows the possibility of leaving the square brackets empty[]. In this case, the **compiler will assume automatically a size for the array that matches the number of values included between the braces {}**

```c++
int foo [] = { 16, 2, 77, 40, 12071 };
```

.

Finally, the evolution of C++ has led to the adoption of **`universal initialization`** also for arrays. Therefore, **there is no longer need for the equal sign** between the declaration and the initializer. Both these statements are equivalent:

```c++
int foo[] = { 10, 20, 30 };
int foo[] { 10, 20, 30 }; 
```

[Detail Array C++](https://www.cpp.edu/~elab/ECE114/Array.html)

- 
```C++
int arrr[15];
cout<< arr[20]; // Exception - Error - You are accessing 20 index but array size is 15
```

- 
```C++
int arr[15] = {2,7};
for(int i =0; i<15; i++){
	cout<<arr[i];   // 270000000000000
}
```

- Initialize all locations with **0**
```C++
int arr[15] = {0};
for(int i =0; i<15; i++){
	cout<<arr[i];   // 000000000000000
}
```


### Array Length 

- First Method to find **Length** of Array

**`sizeof(array)`** returns the total number of bytes used by the array.
```c++
int arr[] = {1,2,3,4,5};
int length = sizeof(arr) / sizeof(arr[0]);  // length = 20/4 = 5 
```

- Second Method to find **Length** of Array
```c++

int getchlength(int num[]) {
  int count = 0;
  for (int i = 0; num[i] != '\0'; i++) {
    count++;
  }
  return count;
}
```

### Array Functions 
- Fill
- Min 
- Max 
- length - size
- sort
- reverse
- swap 
- compare 
- cin 


##### Fill
**`fill:`** This function fills the specified range of an array with a given value. For example, **fill(array, array + n, 0)** sets all elements of the array to 0.

```c++
int arr[5];
fill(arr, arr + 5, 1); // sets all elements of the array to 1
for (int i = 0; i < 5; ++i) {
    cout << arr[i] << " "; // prints: 1 1 1 1 1
}
```



##### Max
Builtin Maximum Function

```c++
int maxx = INT_MIN;

for(int i =0; i< len; i++){
	miaxx = max(miaxx, num[i]);
}
return miaxx;
```

##### Min 

Builtin Minimum Function

```c++
int minn = INT_MAX;

for(int i =0; i< len; i++){
	minn = min(minn, num[i]);
}
return minn;
```

##### Size - Length

- First Method to find Length of Array
```c++
int arr[] = {1,2,3,4,5};
int length = sizeof(arr) / sizeof(arr[0]);  // length = 20/4 = 5 
```

- Second Method to find Length of Array
```c++

int getchlength(int num[]) {
  int count = 0;
  for (int i = 0; num[i] != '\0'; i++) {
    count++;
  }
  return count;
}
```

##### sort 
**`sort:`** This function sorts the elements of an array in ascending order. For example, **sort(array, array + n)** sorts the n elements of the array.

```c++
int arr[] = {5, 3, 1, 4, 2};
sort(arr, arr + 5); // sorts the elements of the array in ascending order
for (int i = 0; i < 5; ++i) {
    cout << arr[i] << " "; // prints: 1 2 3 4 5
}

```


##### reverse
**`reverse:`** This function reverses the order of the elements in an array. For example, **reverse(array, array + n)** reverses the n elements of the array.

```c++
int arr[] = {1, 2, 3, 4, 5};
reverse(arr, arr + 5); // reverses the order of the elements in the array
for (int i = 0; i < 5; ++i) {
    cout << arr[i] << " "; // prints: 5 4 3 2 1
}
```

##### Swap

```c++
int a = 5, b = 10;
swap(a, b); // swap the values of a and b
cout << "a = " << a << ", b = " << b << endl;
```
output
```c++
a = 10, b = 5

```

### Find Min/Max In Array

Minimum
```c++
int mini(int num[], int len){
	
	int min = INT_MAX; 		// #include <bits/stdc++.h>
	
	for(int i =0; i< len; i++){
		if(num[i] < min)
		{
			min = num[i];
		}
		
	}
	return min;
}
```

Builtin Minimum Function

```c++
int minn = INT_MAX;

for(int i =0; i< len; i++){
	minn = min(minn, num[i]);
}
return minn;
```

Maximum
```c++
int maxi(int num[], int len){
	
	int max = INT_MIN;		// #include <bits/stdc++.h>
	
	for(int i =0; i< len; i++){
		if(num[i] > max)
		{
			max = num[i];
		}
	}
	return max;
}
```

Builtin Maximum Function

```c++
int maxx = INT_MIN;

for(int i =0; i< len; i++){
	miaxx = max(miaxx, num[i]);
}
return miaxx;
```

### Types of Array
- int
- char Array 
- float
- double
- bool


## Char Array

Character array is a sequence of characters stored in contiguous memory locations. It is declared as an array of char type.

For example, the following code declares a character array named myString and initializes it with the string "hello":

```c++
char myString[] = "hello";
```

Arrays of type char terminated with null character, that is, **`\0`** (ASCII value of null character is 0)

**null** character **`\0`** is added to the end of the string automatically.

Alternative ways of defining a string:
```c++
  char ch[20];
  
  char str[4] = "C++";

  char str[4] = {'C','+','+','\0'};
```


In Char Array **"Cin >>"** stop Execution when you give him any of these: 
- Space          "__"
- Tab            " \t"
- Enter          "\n"  


**`cin.get()`** reads a single line of input from the stream, including whitespace, and stores it into a character array or a string object.
```c++
char myString[100];
cin.get(myString, 100);
```

- 1. Find **Length** of Char Array
```c++
char myArray[] = "Hello, World!";
int size = sizeof(myArray); // size is 14 (including the null terminator)
```

- 2. Find **Length** of Char Array
```c++
#include <cstring>

char myArray[] = "Hello, World!";
int length = strlen(myArray); // length is 13 (excluding the null terminator)
```

To find the size of a std::**vector<char>** object in C++, you can use the size member function. The **size** function returns the number of elements in the vector.

```c++
#include <vector>

std::vector<char> myVector = {'H', 'e', 'l', 'l', 'o', ',', ' ', 'W', 'o', 'r', 'l', 'd', '!'};
int size = myVector.size(); // size is 13
```

### Practice Questions:
- [REPLIT Char Array Practice](https://replit.com/@ahaniqbal/Char-Array-Reverse-Character-ArrayString#main.cpp)
- LeetCode [Reverse String](https://leetcode.com/problems/reverse-string/) 
- Coding Ninja [Check If The String Is A Palindrome](https://www.codingninjas.com/codestudio/problems/check-if-the-string-is-a-palindrome_1062633#:~:text=Example%20%3A,string%20is%20also%20a%20palindrome.)



![ASSCI Table](https://camo.githubusercontent.com/2d5391bdfdc17f64e1bea83a10af59f0d4852170ff08e336883396f891d40f1e/68747470733a2f2f7072657062797465732d6d6973632d696d616765732e73332e61702d736f7574682d312e616d617a6f6e6177732e636f6d2f6173736574732f313637343535323635323136302d41534349492532305461626c65253230437070312e706e67)






### Find 2nd Largest/ Smallest Number in Array 

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
	int arr[] = {6, 4, 1, 2, 8, 5};
	int max1 = arr[0], max2 = INT_MIN;
	for(int i = 1; i < 6; i++) {
		if(arr[i] > max1 ) {
			max2 = max1;
			max1 = arr[i];
		} else if(arr[i] > max2) {
			max2 = arr[i];
		}
		
	}
	cout << max2 << endl;
	return 0;
}
```
