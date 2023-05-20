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

Method 3: using **For Each** loop

```c++
for(auto x: age)
{
    cout << x.first << " : "	<< x.second << endl;
}
```

Method 4: 

```c++
for(auto itr = age.begin(); itr != age.end(); itr++) {
    cout << itr->first << " : " << itr->second << endl;
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
int arr[10] = {1, 2, 4, 1, 2, 3, 2, 2, 1, 4};

map<int, int> mp;

for(int i = 0; i < 10; i++) {
    int no = arr[i];
    if(mp[no]) {    // {1:2,2:1,3:1}
        mp[no]++;
    }
    else {
        mp[no] = 1;
    }
}

for (auto x: mp) {
    cout << x.first <<  " : " << x.second << endl;
}
```





## Pair 

Pair is used to combine together two values that may be of different data types.


Header file
```c++
#include <bits/stdc++.h>
```

```c++
pair <int, strimg> p;
```


```c++
// defining a pair
pair<int, char> PAIR1;

// first part of the pair
PAIR1.first = 100;
// second part of the pair
PAIR1.second = 'G';

cout << PAIR1.first << " ";
cout << PAIR1.second << endl;
```

**make_pair():** This template function allows to create a value pair without writing the types explicitly. 

```c++
PAIR3 = make_pair("GeeksForGeeks is Best", 4.56);
cout << PAIR3.first << " ";
cout << PAIR3.second << endl;
```

**swap**
```c++
pair1.swap(pair2);
```


## Set 

Sets are a type of associative container in which each element has to be unique because the value of the element identifies it. The values are stored in a specific sorted order i.e. either ascending or descending.

The std::set class is the part of C++ Standard Template Library (STL) and it is defined inside the <set> header file.


Header file
```c++
#include <set>
```
Define Set
```c++
set<int> val; // defining an empty set
set<int> val = {6, 10, 5, 1}; // defining a set with values
```

**insert**
```c++
s.insert(4);
```
##### Iterate Set
1: for each
```c++
for(auto x: s) {
	cout << x << endl;
}	
```

2:
```c++
for (auto itr = s.begin(); itr != s.end(); itr++) {
        cout << *itr << " ";
    }
	
```



