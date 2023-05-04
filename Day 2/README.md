
# Day 2: Char Arrays - Vector Array - String

Topics Day 2:
- **Char Array**
    - Vector Size
    - Char Array Practice Questions
        - Reverse Char Array (String)
        - Check If String is palindrome
- **String** 
    - String Questions
        - Reverse String 
        - Reverse String without moving Special Char
        - Check If String is palindrome
        - Valid Palindrome
        - Reverse Words in a String
        - Remove wovels from string
        - Anagram 
        - Find all anagrams 
        - Sliding Window Approach
        - Palindrom
            - Longest Plendromic Substring
            - Repeated Substring Pattren
            - Longest consective subsequence


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

- 1. Find Length of Char Array
```c++
char myArray[] = "Hello, World!";
int size = sizeof(myArray); // size is 14 (including the null terminator)
```

- 2. Find Length of Char Array
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


## String 

**`string`** is a standard library class that represents a sequence of characters. 

```c++

```


- **Initializing** a string:
```c++
string myString = "Hello, World!";
```

- Finding the **length** of a string:
```c++
int length = myString.length(); // length is 29
```

- Take **Input** string from user:
```c++
getline(cin, student);
```

[String Functions List](https://cplusplus.com/reference/string/string/)

Most used String Functions:

- Size
- length
- getline
- swap
- compare
- push_back
- pop_back

```c++
#include <iostream>
#include <string>
using namespace std;

int main() {
    string str;
    cout << "Enter a string: ";
    getline(cin, str);
    cout << "Size of string: " << str.size() << endl;
    cout << "Length of string: " << str.length() << endl;

    string str2 = "world";
    cout << "Before swap: " << str << " " << str2 << endl;
    swap(str, str2);
    cout << "After swap: " << str << " " << str2 << endl;

    string str3 = "hello";
    cout << "Comparing " << str << " and " << str3 << ": ";
    if (str.compare(str3) == 0) {
        cout << "They are equal" << endl;
    } else {
        cout << "They are not equal" << endl;
    }

    cout << "Enter characters to add to the end of the string: ";
    char c;
    while (cin >> c) {
        str.push_back(c);
    }
    cout << "New string: " << str << endl;

    cout << "Removing characters from the end of the string..." << endl;
    while (!str.empty()) {
        str.pop_back();
        cout << "Current string: " << str << endl;
    }
    cout << "String is now empty" << endl;

    return 0;
}
```

### String Questions 
- [Reverse String](https://replit.com/@ahaniqbal/String-Reverse-String-)
- [344 Reverse String Leet code](https://leetcode.com/problems/reverse-string/description/)
- [Reverse String without moving Special Char](https://replit.com/@ahaniqbal/Reverse-String-without-moving-special)
- [125. Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)
    - [Longest Plendromic Substring]()
    - [Repeated Substring Pattren]()
    - [Longest consective subsequence]()

- [151.  Reverse Words in a String](https://leetcode.com/problems/reverse-words-in-a-string/)
- [557. Reverse Words in a String III](https://leetcode.com/problems/reverse-words-in-a-string-iii/)
- [Remove wovels from string]()
- [Anagram](https://replit.com/@ahaniqbal/Anagram#main.cpp)
- [Valid Anagram](https://leetcode.com/problems/valid-anagram/description/)
    - [Find all anagrams]() 
- [Sliding Window Approach]()
- []()
    




