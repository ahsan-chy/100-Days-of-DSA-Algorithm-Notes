
# Day 5: Array 

Table of Content
- Array 
- Kadane's Algorithm in Array
- Selection Sort in Array

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



## Kadane's Algorithm in Array
```c++
// arr: input array
    // n: size of array
    //Function to find the sum of contiguous subarray with maximum sum.
    long long maxSubarraySum(int arr[], int n){
        // -2, -3, 4, -1, -2, 1, 5, -3
      long long currMax = 0; 
      long long totalMax = INT_MIN;
      for(int i = 0; i < n; i++) {
          currMax += arr[i]; // -2  -5 -1 -2 -4 -3 2 -1                  -2 -3 4 3 1 2 7 4
          totalMax = max(totalMax, currMax); // -2 -2 -1 2            -2 -2 4 7 7
          
          if(currMax < 0) currMax = 0;
          
          
      }
      return totalMax;
    }
```


## Selection Sort

[Visual Algo](https://visualgo.net/en/sorting)

![Selection Sort](https://www.w3resource.com/w3r_images/selection-short.png)

Selection Sort

```c++
int n = 7;
	int arr[] = {4, 3, 3, 2, 10, 12, 1, 5};
	for(int i = 0;i < n; i++) {
		int minIndex = i;
		for(int j = i + 1; j < n; j++) {
			if(arr[j] < arr[minIndex]) {
				minIndex = j;	
			}
		}
		swap(arr[minIndex], arr[i]);
	}
	
	for(int i = 0; i < n; i++) {
		cout << arr[i] << " ";
	}
```