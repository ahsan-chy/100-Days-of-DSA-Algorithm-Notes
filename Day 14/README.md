# Day 14: Searching in Array

Table of Content
- Linear Search
- Binary Search


## Linear Search 
Linear search is defined as a sequential search algorithm, that start from one End and goes through each element.

![linear](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Linear-Search.png)

```c++
int linearsearch(int num[], int N, int x)
{
    for(int i=0; i<N; i++)
        {
            if(num[i] == x)
                return i;
        }
            return -1;
}
```
**Time Complexity**: O(N)
**Space Complexity**: O(1)

## Binary Search 

Binary Search is defined as a searching algorithm used in a sorted array by **repeatedly dividing the search interval in half.** The idea of binary search is to use the information that the array is sorted and reduce the time complexity to **O(log N)**. 

Conditions for when to apply Binary Search in a Data Structure:
- The data structure must be sorted.
- Access to any element of the data structure takes constant time.



![Binary](https://media.geeksforgeeks.org/wp-content/uploads/20230406184038/Binary-Search-GeeksforGeeks.gif)

[Geeks for geeks](https://www.geeksforgeeks.org/binary-search/)

Pseudocode of Iterative  Binary Search Algorithm:

```c++
binarySearch(arr, x, low, high)
    repeat till low = high
           mid = (low + high)/2
           if (x = arr[mid])
               return mid
          else if (x > arr[mid])
               low = mid + 1
          else
               high = mid – 1
```

##### Code
```c++
int binarysearch(int num[], int N, int x)
{
	int l = 0;
	int r = N-1;
	
	while (l <= r) {
		int mid = l + (r - l) / 2;

		// Check if x is present at mid
		if (arr[mid] == x)
			return mid;

		// If x greater, ignore left half
		if (arr[mid] < x)
			l = mid + 1;

		// If x is smaller, ignore right half
		else
			r = mid - 1;
	}

	// if we reach here, then element was not present
	return -1;
}

```


![Binary search](https://media.geeksforgeeks.org/wp-content/uploads/20220309171621/BinarySearch.png)


### Binary Search Questions 

- First and Last Position of an Element In Sorted Array
- 852. **Peak Index of Mountain Array** 
- Book Alocation Problem



#### First and Last Position of an Element In Sorted Array


- First Occurance - Last Occurance
- Upper bound - Lower Bound
 

[Geeks for Geeks Explanation](https://www.geeksforgeeks.org/find-first-and-last-positions-of-an-element-in-a-sorted-array/)


[Coding Ninja](https://www.codingninjas.com/codestudio/problems/first-and-last-position-of-an-element-in-sorted-array_1082549)

[34. Leet code](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/)


```c++

int firstOccurance(int arr[], int n, int key){

	int low = 0;
	int high = n;
	int mid = low + (high - low) / 2;
	int ans = -1;
	
	while(low <= high){
		
		if(arr[mid] == key){
			ans = mid;	
			high = mid -1;  	//First Occurance 
		}
		else if(key > arr[mid]){
			low = mid + 1;
		}
		else {
			high = mid -1;
		}
		mid = low + (high - low) / 2;
	}
	return ans;
}

int lastOccurance(int arr[], int n, int key){

	int low = 0;
	int high = n;
	int mid = low + (high - low) / 2;
	int ans = -1;
	
	while(low <= high){
		
		if(arr[mid] == key){
			ans = mid;	
			low = mid + 1;	// Last Occurance  
		}
		else if(key > arr[mid]){
			low = mid + 1;
		}
		else {
			high = mid -1;
		}
		mid = low + (high - low) / 2;
	}
	return ans;
}
```

```c++
int even[] = {1,2,3,3,3,3,3,5};
int first = firstOccurance(even, 9, 3);
int last = lastOccurance(even, 9, 3);
```

##### Find total number of occurance of 3

```c++
(last - start) +1  //(5-2) + 1 = 4
```

.

#### 852. Peak Index of Mountain Array

Geeks for Geeks Question
- [Find the maximum element in an array which is first increasing and then decreasing](https://www.geeksforgeeks.org/find-the-maximum-element-in-an-array-which-is-first-increasing-and-then-decreasing/)