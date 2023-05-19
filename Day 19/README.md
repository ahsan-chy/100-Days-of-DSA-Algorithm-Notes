# Day 19: Vector

Table of Content
- Vector 
- Header Files
- Vector Data types
- Vector Functions 
- Iterate in Vector


vector is a dynamic array that can automatically resize itself as elements are added or removed. It is part of the Standard Template Library (STL) and is defined in the **`<vector>`** header file.


#### Header Files:
```c++
#include <iostream>
#include <vector>
using namespace std;
```

Different Type of Vector define methods:
- vector **<int>** myVector
- vector **<char>** charVector;
- vector **<string>** stringVector;
- vector **<double>** doubleVector;
- vector **<bool>** boolVector;


.

Common Functions in Vector 
- push_back
- pop_back
- size()
- capacity
- erase
- clear
- empty
- reverse
- **Iterate** Vector
- Swap
- Sort
- Begin - End

**Define** Vector 
```c++
vector<int> v; 
```

**Push** Element in Vector
```c++
v.push_back(5);
```

```c++
v.emplace_back(10);
```


**Push** at Front position
```c++
v.emplace(v.begin(), 10000);
```

.

**Pop** Element
```c++
v.pop_back();
```




**size** of Vector
```c++
v.size()
```

**capacity** of Vector
```c++
v.capacity()
```

**Erase** at Front position
```c++
// stl => iterator: pointer to a specific position (address)
// begin(), array first index
// end() array last element k just bad wala adress
// 1 2 3 garbage
v.erase(v.begin(), v.begin()+2); // inclusive exclusive

```

**clear** values of Vector
```c++
v.clear()
```

**empty** values of Vector
```c++
v.empty()
```
Example
```c++
 // Check if the vector is empty
    if (myVector.empty()) {
       cout << "Vector is empty.";
    }
```

**reserve** values of Vector
```c++
v.reserve()
```


#### Iterate Vector 
```c++
for(int i = 0; i < v.size(); i++) {
    cout << v[i] << " ";
}
```

**swap** values of Vector
```c++
swap(first, second);
```

**Sort**
```c++
// array sort
std::sort(v.begin(), v.end());
```





**begin**

**end**


[VEctor Functions](https://cplusplus.com/reference/vector/vector/)
