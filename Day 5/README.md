# Day 5:  Time & Space Complexity


Table of Content
- Time Complexity 
- Space Complexity 
- Auxiliary Space
- Big-O Notation (O-notation)
- Theta Notation (Θ-notation)
- Omega Notation (Ω-notation)
- TLE - Time Limit Excide



.


**Time complexity** is a function that describes how long an algorithm takes in terms of the quantity of input it receives. 

**Space complexity** is a function that describes how much memory (space) an algorithm requires to the quantity of input to the method.

.

**Auxiliary Space** is the extra space or temporary space used by an algorithm.

Note: It’s necessary to mention that space complexity depends on a variety of things such as

- the programming language,
- the compiler, or
- even the machine running the algorithm.


.

![Time and Space Complexity](https://i.ytimg.com/vi/bxgTDN9c6rg/maxresdefault.jpg)

There are mainly three asymptotic notations:

- Big-O Notation (O-notation)
- Omega Notation (Ω-notation)
- Theta Notation (Θ-notation)


## Big-O Notation (O-notation)

Big-O notation represents the **upper bound** of the running time of an algorithm. Therefore, it gives the **worst-case** complexity of an algorithm.



## Theta Notation (Θ-notation)
Theta notation encloses the function from above and below. Since it represents the upper and the lower bound of the running time of an algorithm, it is used for analyzing the **average-case** complexity of an algorithm.  

## Omega Notation (Ω-notation)
Omega notation represents the **lower bound** of the running time of an algorithm. Thus, it provides the **best case** complexity of an algorithm.



![asymtotic notation](https://adrianmejia.com/images/time-complexity-examples.png)



## TLE - Time Limit Excide

Most of the sites these days allow **10^8** operations per second, only a few sites still allow **10^7** operations. After figuring out the number of operations that can be performed, search for the right complexity by looking at the constraints given in the problem. 



![TLE](https://media.geeksforgeeks.org/wp-content/uploads/20230308145710/Screenshot_20230308_025553.png)