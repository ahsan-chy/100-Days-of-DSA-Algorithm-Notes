# Day 12: Array Approches

Table of Content
- Two Pointer Approch
- Palindrom
- Anagram 
- Kadane's Algorithm in Array
- Sub Array 
- Sliding Window
    - Minimum Sub Array 
    - Maximum Sub Array
- **Dublicate** in Array 
    - Find Dublicate in Array
    - Find Unique Element In Array
    - Remove Dublicate in Array
- Fast - Slow Approch (Rabbit & Turtol Approch)
-  Find Missing in Array
- 




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

## Sub Array 



## Sliding Window 



![Sliding Window](https://algomonster.s3.us-east-2.amazonaws.com/sliding_window_maximum.png)

![Sliding Window](https://miro.medium.com/v2/resize:fit:1135/1*i_lXNFGO36nh671aziwrUA.jpeg)


#### First Approch



```c++
int slidingWindow(int arr[], int size, int window) {
	
	int output[size - window +1];

	for(int i =0; i< size - window +1; i++){
		int sum = 0;
		for(int j = i; j< window + i; j++){
			sum = sum + arr[j];
			output[i] = sum;
		}
	}

	int max = INT_MIN;
	int len = getchlength(output);
	for(int x = 0; x< len; x++){
		if(output[x] > max)
		{
			max = output[x];
		}		
	}	
	return max;
}

```

Find **Length** of Array 
```c++
//Get Length of Array
int getchlength(int ch[]) {
  int count = 0;
  for (int i = 0; ch[i] != '\0'; i++) {
    count++;
  }
  return count;
}
```
#### Optimal Approch

```c++
#include <bits/stdc++.h>
using namespace std;
	
int kGroupSum (int arr[], int n, int k) {
		int mSum = 0;
		int sum = 0;
		for(int i = 0; i < k; i++) {
			mSum += arr[i];
		}
		sum = mSum;
		for(int i = k; i < n; i++) {
			sum += arr[i];
			sum -= arr[i-k];
			mSum = max(sum, mSum);
		}
		return mSum;
	}
int main() {
	int arr[] = {5, 6, 1, 2, 3, 10};
	cout << kGroupSum(arr, 6, 1) <<endl;
}

```



### Find Unique

- Find Unique Elements in Array 
- Array all elements apprear twice only one appear once

```c++
int findUnique(int *arr, int n){
	int ans = 0;
	for(int i =0; i< n; i++){
		ans = ans ^ arr[i]; 
	}
	return ans;
}
```

Find All Elements which Appear only Once in Array
```c++

```

### Find Dublicate

```c++
int findUnique(int *arr, int n){
	int ans = 0;
	for(int i =0; i< n; i++){
		ans = ans ^ arr[i]; 
	}

	for(int j=0; j< n; j++){
		ans = ans ^ j;
	}
	return ans;
}
```

Find All Elements which Appear Twice in Array
```c++

```


### Find the Missing Number

[Geeks For Geeks](https://www.geeksforgeeks.org/find-the-missing-number/) 

##### When Array is
- Sorted Array
	- Linear Search (Approch)
	- Binary Search (Approch)
- Unsorted Array


##### Other Approches
- Hash
- 


##### Brute Force
```c++
// Function to get the missing number
int getMissingNo(int a[], int n)
{
    // Given the range of elements
    // are 1 more than the size of array
    int N = n + 1;
   
    int total = (N) * (N + 1) / 2;
    for (int i = 0; i < n; i++)
        total -= a[i];
    return total;
}
```