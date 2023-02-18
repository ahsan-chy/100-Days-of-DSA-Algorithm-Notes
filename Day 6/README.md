
# Day 6

Table of Content
- Bubble Sort 
- Auxilary Space
- InPlace
- Bitwise Operator
- Swap with **XOR** without Third Variable
- IF - Else (Optimize way to write)


.

## Bubble Sort
[Geeks for Geeks Bubble Sort](https://www.geeksforgeeks.org/bubble-sort/)
```javascript
function swap(arr, first, second){
	let temp = arr[first];
	arr[first] = arr[second];
	arr[second] = temp;
}
function bubbleSort(arr)
	{
		n = arr.length;
		for(let i = 1; i<n; i++)
			{
				for(let j = 0; j < n-i; j++ )
					{
						if(arr[j] > arr[j+1])
						{
							swap(arr, j, j+1)
						}
					}
			}
		return arr;
	}

console.log(bubbleSort([2,3,1,4,6,5]))
```
![Bubble sort](https://miro.medium.com/max/556/0*lq-ZpDYjvYGmS7PO)

## Auxilary Space 
Auxiliary Space is the extra space or temporary space used by an algorithm.

**Note:** It’s necessary to mention that space complexity depends on a variety of things such as 
- the programming language, 
- the compiler, or 
- even the machine running the algorithm.






## In Place
An in-place sorting algorithm uses **constant space for producing the output (modifies the given array only).** It sorts the list only by modifying the order of the elements within the list.

Many sorting algorithms rearrange arrays into sorted order In-place, including: 
-  bubble sort, 
-  selection sort, 
-  insertion sort, 
-  heapsort, and 
-  Shell sort. 
-  Quicksort operates in-place on the data to be sorted.

These algorithms require only a few pointers, so their space complexity is **O(log n).** 

An **in-place sorting** algorithm sorts the elements in place: that is, it needs only **`O(1) extra space.`** An **out-of-place sorting** algorithm needs extra space to put the elements in as it's sorting them. Usually this means **`O(n) extra space`**.


## Bitwise Operator

[C++ Bitwise Operator](https://www.programiz.com/cpp-programming/bitwise-operators)

![screenshot-www programiz com-2023 02 17-14_40_26](https://user-images.githubusercontent.com/85479513/219609305-a76a0e53-0e89-4365-8557-ddd2408b6702.png)


## Swap with **XOR** without Third Variable

[Reference Video Link](https://youtu.be/L7OeXaFrbmU)

**Example 1:**
```javascript
let x = 10, y = 5;

// Code to swap 'x' (1010) and 'y' (0101)

x = x ^ y; // x now becomes 15 (1111)
y = x ^ y; // y becomes 10 (1010)
x = x ^ y; // x becomes 5 (0101)

After Swapping: x =5, y=10
```
- **Time Complexity:** O(1).
- **Auxiliary Space:** O(1).
[Geeks for Geeks Explanation: ](https://www.geeksforgeeks.org/swap-two-numbers-without-using-temporary-variable/)


**Example 2:**
```c++
arr[j] = arr[j] ^ arr[j+1];
arr[j+1] = arr[j] ^ arr[j+1];
arr[j] = arr[j] ^ arr[j + 1];
```
![xor](https://electronicspost.com/wp-content/uploads/2015/11/truth-table-of-ex-or-gate.png)







## If - Else (Optimize Way to write)



