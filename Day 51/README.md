# Day 51: Hashmap - Set - Pair 

Table of Content
- Hashmap
    - Create Hashmap
    - insertion
    - find
    - Size
    - Presence
    - iterate hashmap
- Hashmap Common Questions
- Map
- Set


### Hashmap 
A **hash map**, also known as a **hash table** or dictionary, is a data structure that allows efficient storage and retrieval of **key-value** pairs. 

Hash maps have a constant time complexity O(1) for **`insertion, deletion, and retrieval`** on average, making them highly efficient for handling large amounts of data.


Related Stuff:
- Map **O(log(n))**
- Unordered Map **O(1)**

[Geeks for Geeks - unordered_map in C++ STL](https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/)

.


Include Header Files
```c++
#include <iostream>
#include <unordered_map>
using namespace std;
```

### Creation

Creation of hashmap
```c++
unordered_map<string, int> age;
```

### Insertion

Method 1
```c++
pair<string, int> p = make_pair("ahsan", 24);
age.insert(p);
```

Method 2
```c++
age["Salahudin"] = 10;
```


### Find / Search

```c++
cout<<age["ahsan"]<<endl;
```
Search  at position
```c++
cout<<age.at("Salahudin")<<endl;
```
Search at position which not exist. If position `hashim` doesn't exist it put it's value 0 and 
```c++
cout<<age["hashim"]<<endl;
cout<<age.at("hashim")<<endl;
```


### Size

```c++
age.size()
```

### Check Presence

If **`key`** is Present then it will return **1** otherwise it will return **0**.
```c++
age.count("anonymous")  // return 0 
age.count("Salahudin")  // return 1
```

### Erase the Element

```c++
age.erase("hashim")
```



### Iterate Hashmap

Method 1: using **While** loop

```c++
unordered_map<string,int> :: iterator it = age.begin();

while(it != age.end()){
    cout<< it->first <<" " << it->second <<endl;
    it++;
}
```

Method 2: using **For** loop

```c++
unordered_map<string, int> :: iterator itr;
 
	 for (itr = age.begin(); itr != age.end(); itr++) 
  { 
		cout << itr->first << "  " << 
            itr->second << endl;
  }
	
```

Iterate **Map**

```c++

```

## Hashmap Common Questions
- Save Frequency of Array Elements
- 
- 

### Save `frequency` of arry Elements

```c++

```



