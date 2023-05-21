# Day 12: Array Approches

Table of Content
- Sub Array - Sub Sequence
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
- Move Zero **0** at end
- 




### Sub Array 
- Sub Array 
- Sub Sequence

A subarray is a contiguous subset of the array. Contegious part of array. 

arr[] = {-2, -3, 4, -1, -2, 1, 5, -3}

Example of **Sub array**:
sub = {4, -1}
sub = { 1, 5, -3}
sub = {-2, -3, 4, -1, -2, 1, 5, -3}

Sub array can be any single element or entire array or any specific sequence of array elements. 


![Sub array](https://www.interviewbit.com/blog/wp-content/uploads/2021/09/Array.jpg)


### Sub Sequence 

arr[] = {-2, -3, 4, -1, -2, 1, 5, -3}

subsequence: {4, -1, 5}
subsequence: {-2, -1, -3}

![Subarray](https://prepinsta.com/wp-content/uploads/2021/12/Python-program-to-find-Largest-sum-of-contiguous-Subarray.webp)


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

##### Remove duplicates from Sorted Array
[Geeks for Geeks Explanation](https://www.geeksforgeeks.org/remove-duplicates-sorted-array/)

Method 1: 
```c++
 int removeDublicate(int arr[], int n){
	 if( n == 0 || n == 1) return n;

	 int temp[n];
	 int j =0;

	 for(int i= 0; i<n-1; i++){
		 if(arr[i] != arr[i+1]){
			 temp[j++] = arr[i];
		 }
	 }
	 temp[j++] = arr[n-1];

	 for(int i = 0; i<j; i++){
		 arr[i] = temp[i];
	 }
	 return j;
 }
```

```c++
int arr[] = {1, 2, 2, 3, 4, 4, 4, 5, 5}; // Text case 1
int arr1[] = {25};	// Text case 2
int arr2[] = {1,1,1, 2, 2, 3, 4, 4, 4, 4, 5, 5}; // Text case 3
int arr3[] = {11,11,12, 12, 12, 33, 34, 44, 24, 24, 25, 55}; // Text case 4
int n = sizeof(arr) / sizeof(arr[0]);
int n1 = sizeof(arr1) / sizeof(arr1[0]);
int n2 = sizeof(arr2) / sizeof(arr2[0]);
int n3 = sizeof(arr3) / sizeof(arr3[0]);

int length = removeDublicate(arr, n);
cout<<length <<endl;

for(int i=0; i<length; i++){
	cout<<arr[i] << " ";
}
```

Method 2:
```c++
int removeDublicate(int arr[], int n){
	if (n==0 || n==1)
        return n;
	int j = 0;
	for(int i =0; i < n-1; i++){
		if(arr[i] != arr[i+1]){
			arr[j++] = arr[i];
		}
	}
	arr[j++] = arr[n-1];
	return j; 
}
```

Method 3: Amir Method
```c++
int removeDuplicate(int arr[], int n) {
	int j = 0; // 0 
	for(int i = 1; i < n; i++) {
		if(arr[i] == arr[j]) continue;

		arr[++j] = arr[i];
	}
	j++;
	return j;
}
```


Find All Elements which Appear Twice in Array
```c++

```


### Find the Missing Number

[Explanation Interview bit](https://www.interviewbit.com/blog/find-the-missing-number/)
![Find missing](https://www.interviewbit.com/blog/wp-content/uploads/2021/10/Missing-Number.jpg)

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
```diff
! Brute Force Approch 
int missingNumber(int arr[], int n)
{
	int total = (n+1) * (n+2)/2; 
	for(int i =0; i<n; i++){
		total -= arr[i];		
	}
	return total;
}

int main() {
	int arr[] = {1,2,3,5,6,7};
	cout<<missingNumber(arr,6);
}
```

##### Using **XOR** Approch


**Algorithm:**
- Create two variables a1= 0 and a2 = 0
- Iterate from 1 to n with i as the counter.
- For every index i update a1 as a1 = a1 ^ i
- Now iterate over the array from start to end.
- For every index i update a2 as a2 = a2 ^ arr[i]
- Print the missing number as a1 ^ a2.


```c++
int MissingNo(int arr[], int n) {
  int x1 = arr[0];
  int x2 = 1;

  for (int i = 1; i < n; i++)
    x1 = x1 ^ arr[i];

  for (int i = 2; i <= n + 1; i++)
    x2 = x2 ^ i;

  return (x1 ^ x2);
}
```


### Move all zeroes 0 to end of array

Two Ways to resolve this:
- In-Place Allowed
- In-Place Not Allowed

Method : **Partitioning the array / Two Pointer**

**Approach**: The approach is pretty simple. We will use 0 as a pivot element and whenever we see a non zero element we will swap it with the pivot element. So all the non zero element will come at the beginning.



```c++
void movezero(int arr[], int n) {
    int z = 0;  // Index to track the position of the next non-zero element
    
    for (int i = 0; i < n; i++) {
        if (arr[i] != 0) {
            // Swap the non-zero element with the element at position 'z'
            swap(arr[z], arr[i]);

            z++;  // Increment 'z' to point to the next position for a non-zero element
        }
    }
}

  int arr[] = {4, 0, 1, 0, 2, 3, 0, 5, 6, 7};  
  movezero(arr, 10);
	for(int i = 0; i < 10; i++)
		cout << arr[i] << " ";
```


##### Char Array & String move 'a' at end
```c++
void moveA(char arr[], int n){
	int z = 0;
	for(int i = 0; i < n; i++) {
		if(arr[i] != 'a') {
			char tmp = arr[i];
			arr[i] = arr[z];
			arr[z] = tmp;
			z++;
		}
	}
}
string moveLang(string &str){
	int n = str.length();
	int z = 0;
	for(int i = 0; i < n; i++) {
		if(str[i] != 'a') {
			char tmp = str[i];
			str[i] = str[z];
			str[z] = tmp;
			z++;
		}
	}
	return str;
}
```
int main()
```c++
 char str[] = {'t', 'a', 'b', 'a', 'b', 'n', 'c', 's', 'a', 'a', '\0'};  
  string lang = "ahsan";  

moveA(str, 10);
	for(int i = 0; i < 10; i++)
	cout << str[i] << " ";

moveLang(lang);
	cout << lang << " ";
```
