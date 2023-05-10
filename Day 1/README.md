## Day 1 

Table of Content
- Data Type in C++
- Data Unit
- ASCII Table
- Increment - Decrement
- If - If Else Statement (Return) 
- Swap Two Numbers (without using third variable)
- Break - Continue
- 


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

### Topic 1: INC - DEC

[Practice Refference](https://javaconceptoftheday.com/quiz-on-increment-and-decrement-operators/#collapse1)



```javascript
while(i<n1 && j<n2)
{
	if(left[i] < right[j]){
      arr[6] = left[0]
			arr[k++] = left[++i]    //Post Inc - Pre Dec       
	}else{
			arr[k++] = right[++j];  //Post Inc - Pre Dec
	}
}
```
![Inc - Dec](https://d1whtlypfis84e.cloudfront.net/guides/wp-content/uploads/2021/05/16092414/Copy-of-Copy-of-Heading-1-2.png)

### Topic 2: Swapping two variables
[JavaScript Swap Two variables](https://replit.com/@ahaniqbal/Day-1-Swap-two-variables#index.js)

[C++ Swap Two variables](https://replit.com/@ahaniqbal/swap-two-variables#main.cpp)

![Swap two values](https://i1.faceprep.in/Companies-1/swap-two-variables-in-python.png)


### Topic 3: If - If Else

```c++
void push(int val) {
	if( top == 9) return;       //If Condition
	arr[++top] = val;           // Else Part - After If fail
}
```
```c++
int pop() {
	if(top < 0) return -1;       //If Condition
	return arr[top--];           // Else Part - After If fail
}
```

