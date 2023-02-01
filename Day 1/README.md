## Day 1
- Increment - Decrement
- If - If Else Statement (Return) 
- Swap Two Numbers (without using third variable)

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

