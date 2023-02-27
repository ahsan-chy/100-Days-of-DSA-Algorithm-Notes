
## Binary & Decimal Number System

- Decimal to Binary 
- Decimal to Binary

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