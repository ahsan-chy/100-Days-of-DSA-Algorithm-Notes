
## Array 

- What is Array
- Sorting in Array
- Searching in Array
- Traverse Array
- Find Element in Array
	- Compare Values in Array
	- Min - Max
	- Find 2nd last element 
- Filter Array 
- Push/Insert Element in Array
- PoP/Remove/Delete Element in Array

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


