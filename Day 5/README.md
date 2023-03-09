
# Day 5: Array 

Table of Content
- Data Type in C++
- Data Unit
- ASCII Table
- One's Complement - Two's Complement
- Array 
- Kadane's Algorithm in Array
- Selection Sort in Array

.

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

#### One's Complement - Two's Complement

![One's two](https://delightlylinux.files.wordpress.com/2014/10/l12-2.png)

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

#### Selection Sort

```c++
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
