# Day 7: Number & Math Operations

Topics Day 7:
- **Number** 
    - Number Questions
        - Count Digits
        - Reverse given Number
		- Strong Numbers 
        - Number is Armstrong
        - Number is palindrom or Not
		- Sum of digits of a number until sum becomes single digit
        - Print All Divisor of Given Number 
		- Decimal to Binary 
		- Binary to Decimal
		- Toggle Numbers
		- Find Even - ODD 
		- Find 2nd Largest Num
		- Factorial of a number
		- Fabnocci Series
        - Find GCO Of Two Numbers 


### Number Questions

- [Count Digits]()
- [Reverse given Number](https://replit.com/@ahaniqbal/Reverse-Number#main.cpp)
- [Strong Numbers](https://replit.com/@ahaniqbal/strong-Number-c#main.cpp)
- [Number is Armstrong]()
- [Number is palindrom or Not](https://replit.com/@ahaniqbal/Palindrom-Number)
- [Sum of digits of a number until sum becomes single digit](https://replit.com/@ahaniqbal/ESketchers-4179)
- [Print All Divisor of Given Number]() 
- [Decimal to Binary]() 
- [Binary to Decimal]() 
- [Toggle Numbers]() 
- [Find Even - ODD ]() 
- [Find 2nd Largest Num]() 
- [Factorial of a number]() 
- [Fabnocci Series]() 
- [Find GCO Of Two Numbers]() 


## Reverse the Number 

```c++
int reverseData(int n) {
	cout<<n<<endl;

  int reverseNumber = 0;		  //123 
  while (n) {
    int last = n % 10;				// 3 2 1
    reverseNumber = reverseNumber * 10 + last;	// 321
    n = n / 10;							// 12 1 0
  }
  return reverseNumber;
}
```

## Strong Number 

**Strong number** is a special number whose sum of the factorial of digits is equal to the original number. 

For Example: 145 is strong number. Since, **1! + 4! + 5! = 145.**

![Strong number](https://www.w3resource.com/w3r_images/c-for-loop-image-exercises-47.png)


#### Print all Strong numbers less than or equal to N

```c++
int fact(int n){
    int f = 1;
    for(int i=n;i>=1;i--){
        f = f*i;
    }
    return f;
}
bool strong(int n){
    int sum = 0; // 0
    int n1 = n; // 145 
    while(n1){
        int last = n1%10; // 5 4 1
        sum += fact(last); // 144 + 1
        n1 = n1/10; // 14, 1 , 0
    }
    if(sum == n)
        return true;
    return false;
}

int main(){

 	for(int i=1;i<=100000;i++)
 		if(strong(i))
		cout<<"strong: "<<i<<endl;
}
```



## Armstrong Number 

![Armstrong Number](https://i1.faceprep.in/Companies-1/armstrong-number-in-python.png)



## Number is Palindrom 

```c++
int reverseData(int n) {
	cout<<n<<endl;

  int reverseNumber = 0;		  //123 
  while (n) {
    int last = n % 10;				// 3 2 1
    reverseNumber = reverseNumber * 10 + last;	// 321
    n = n / 10;							// 12 1 0
  }
  return reverseNumber;
}
```

## Finding sum of digits of a number until sum becomes single digit

[Geeks For Geeks Example](https://www.geeksforgeeks.org/finding-sum-of-digits-of-a-number-until-sum-becomes-single-digit/)

Example:  
```c++
7654  // 7 + 6 + 5 + 4
22   // 2 + 2
4	// Output
```

```c++
int num;
cout<<"Enter Number"<<endl;
cin>>num;

int temp = num;
while(temp > 9){
	int sum =0;
	while(temp > 0){
		
		int last = temp %10;
		sum += last;
		temp = temp/10;
	}
	cout<<sum<<endl;
	
	temp = sum;
}
```

.


![Binary table](https://miro.medium.com/max/1152/1*DTmuXRaK9GIqeEF9IB2B_g.png)

First Method to **Convert Decimal to Binary**
```c++
    string ans = "";  // answer 
	int number = 10; 
	while(number) {
		char rem = number & 1 ? '1' : '0'; //Check Remainder= 0 - 1  
		ans = rem + ans; 
		number = number >> 1; // 0 5 2 1 0
	}
	cout << ans << endl;
```

![Decimal to binary](https://i1.faceprep.in/Companies-1/decimal%20to%20binary.png)

.

Second Method to **Convert Decimal to Binary**
```c++
	string ans = "";   
	int number = 10; 
	while(number != 0) {
		char rem = number % 2 ? '0' : '1'; //Check Remainder= 0 - 1
		ans = rem + ans; 
		number = number / 2; // 0 5 2 1 0
	}
```


#### number & 1  -  number % 2  

This is basically use to check **remainder** is 0 or 1

```c++
// ---- Check Even - ODD ----//
	int number = 4;
	char rem = number & 1 ? 'O' : 'E';    //1010 & 0001 = 0000 => 0
	cout<<rem; // If Condition True - ODD - Else - Even;
```


Third Method to **Convert Decimal to Binary**

```javascript
	int num = 10;
	
	int i = 0;
	int ans = 0;
	while(num !=0)
		{
			int bit = num %2;
			ans = (bit * pow(10, i)) + ans;
			num /= 2;
			i++;
		}
  cout<<ans;
```

Optimize Syntax:
```C++
	int num = 5;
	
	int i = 0;
	int ans = 0;
	while(num)
		{
			int bit = num & 1;
			ans = (bit * pow(10, i)) + ans;
			num = num >>1;
			i++;
		}
  cout<<ans;
```

.

**-Ve Number** Binary:
```C++
int num = -10;
	num = ~num + 1;  // Two's complement (Onex complement +1)
	int i = 0;
	int ans = 0;
	while(num !=0)
		{
			int bit = num & 1;
			ans = (bit * pow(10, i)) + ans;
			num = num >>1;
			i++;
		}
  cout<<ans;
```


![Binary to decimal](https://www.inchcalculator.com/wp-content/uploads/2021/09/how-to-convert-binary-to-decimal-thumb.png)

#### Binary to Decimal

```C++
#include <math.h>

	int num = 10101;
	int i =0;
	int res = 0;
	while(num)
		{
			int digit = num % 10;

			if(digit ==1)
			{
				res = res + pow(2, i);
			}
			
			num = num / 10;
			i++;
		}

	cout<<res;
```


## Toggle Numbers

- Make a function in which users pass 2 inside the function parameter and the function will return 3 and if user pass 3 it will return 2.

IN javascript
```javascript
function reverse(val) {
    let result = {
        1: 2, 
        2: 1
    }
    return result[val]

}
console.log(reverse(1))
```


Optimal Solution - **XOR**
```c++
int swapValues(int num) {
    return (num ^ 9) ^ 3;  
}
```
Explanation:

number ^ 0 = number

number ^ number = 0 

.


## Find Even - ODD 




#### Find Even-Odd without using if-else
```c++
string toggle(int num) {
	string arr[] = {"even", "odd"};
	return arr[num%2];
}
```


## Find 2nd Largest Num

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
	int arr[] = {6, 4, 1, 2, 8, 5};
	int max1 = arr[0], max2 = INT_MIN;
	for(int i = 1; i < 6; i++) {
		if(arr[i] > max1 ) {
			max2 = max1;
			max1 = arr[i];
		} else if(arr[i] > max2) {
			max2 = arr[i];
		}
		
	}
	cout << max2 << endl;
	return 0;
}
```

## Factorial of a number

```
n! = n * (n – 1)!

n! = 1 if n = 0 or n = 1
```

[Details on Geeks for Geeks](https://www.geeksforgeeks.org/program-for-factorial-of-a-number/)

Recurision Approch
```c++
unsigned int factorial(unsigned int n)	//Unsigned mean +ve Value
{
    if (n == 0 || n == 1)
        return 1;
    return n * factorial(n - 1);
}
```

Iteration 
```c++
unsigned int factorial(unsigned int n) //Unsigned mean +ve Value
{
    int res = 1, i;
    for (i = 2; i <= n; i++)
        res *= i;
    return res;
}
```


## Fabnocci Series

0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, ……..

```
Fn = Fn-1 + Fn-2

F0 = 0 and F1 = 1.
```

[Details Geeks for Geeks](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/)

Recurission
```c++
int fib(int n)
{
    if (n <= 1)
        return n;
    return fib(n - 1) + fib(n - 2);
}
```

Iteration
```c++
int fib(int n)
{
    int a = 0, b = 1, c, i;
    if( n == 0)
        return a;
    for(i = 2; i <= n; i++)
    {
       c = a + b;
       a = b;
       b = c;
    }
    return b;
}
```



