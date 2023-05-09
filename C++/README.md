
# C++ Notes

  - C++ Header Files
  - Return Types (Void Main - Int Main) 
  - Max Int
  - Min Int 
  - Input Output
  - Data Types in C++

### C++ Header File
```c++
#include <iostream>     
#include <bits/stdc++.h>  //Header File for everything - Not Recomended nromally
using namespace std;
```

### Return Types (Void Main - Int Main)
Void means nothing.
- The **`void sum()`** indicates that the sum() function **will not return any value,**.

- **`int main()`** indicates that the main() **can return integer type data.**

- **`long main()`** indicates that the main() **can return long type data.**

.

#### MAX_INT
```c++
#include <bits/stdc++.h>
```
```c++
  cout << INT_MAX;  //2147483647123
```
#### MIN_INT
```c++
#include <bits/stdc++.h>
```
```c++
  cout << INT_MIN;  //-2147483648
```

### Input - Output
```c++
cin >> x;   // Take user input
cout << x;  // Display Output
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

.

Take **Input string** from user:
```c++
getline(cin, student);
```

## Data Type in C++
![Data Type in C++](https://www.sitesbay.com/cpp/images/data-type-in-cpp.jpg)

[Data Types in Detail](https://www.sitesbay.com/cpp/cpp-datatype)

```c++
Size of char : 	1 byte
Size of int : 	4 bytes
Size of short int : 2 bytes
Size of long int :  8 bytes
Size of signed long int : 	8 bytes
Size of unsigned long int : 8 bytes
Size of float :   4 bytes
Size of double :  8 bytes
Size of wchar_t : 4 bytes
```
![Size of c++ Data Types](https://miro.medium.com/max/1400/1*YrL7gZ84SyjtUJJIXnsO4g.png)


![Data Unit](https://image.semiconductor.samsung.com/image/samsung/p6/semiconductor/suppport/toolsandresources/dictionary/bits-and-bytes-units-of-data_2_en.jpeg?$ORIGIN_JPG$)

ASCII Table

![ASCII](https://prepbytes-misc-images.s3.ap-south-1.amazonaws.com/assets/1674552652160-ASCII%20Table%20Cpp1.png)
