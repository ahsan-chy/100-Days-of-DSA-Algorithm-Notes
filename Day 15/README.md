# Day 15: Sorting in Array

Table of Content
- Selection Sort 
- Bubble Sort 
    - Auxilary Space
    - InPlace


.


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


.



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



