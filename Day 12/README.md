# Day 12: 

Table of Content
- Two Pointer Approch
- Palindrom
- Anagram 
- Sliding Window
- **Dublicate** in Array 
    - Find Dublicate in Array
    - Find Unique Element In Array
    - Remove Dublicate in Array
- Kadane's Algorithm in Array
- Fast - Slow Approch (Rabbit & Turtol Approch)
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

