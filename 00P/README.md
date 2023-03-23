
# OOP

Table Of Content
- Struct vs Class
- This
- Address in C++
- Pointer
- Virtual Function 
- Abastract Class
- Pure Virtual Function
- Abstract Class - Interface
- Friend Function
- Friend Class


## Struct vs Class

Class: 
- Members of a class are **private by default.**
- It is declared using the **class** keyword.
- Base classes/structures of a class are private by default.
- It support inheritance.
- It can have NULL values
- It is refference type
- It may have all the types of constructors and destructors.

Structure:
- Members of a structure are **public by default.** 
- It is declared using the **struct** keyword.
- Base classes/structures of a structure are public by default.
- It does not support inheritance.
- It cannot have NULL values.
- It is value type.
- It may have only parameterized constructor.

## This 

this is a keyword that **refers to the current instance of the class.** 
 There can be 3 main usage of this keyword in C++. 

- It can be used to **pass current object as a parameter to another method.** 

- It can be used to **refer current class instance variable.**

Example:

```javascript
#include <iostream>
using namespace std;
class Demo {
private:
  int num;
  char ch;
public:
  void setMyValues(int num, char ch){
    this->num =num;
    this->ch=ch;
  }
  void displayMyValues(){
    cout<<num<<endl;
    cout<<ch;
  }
};
int main(){
  Demo obj;
  obj.setMyValues(100, 'A');
  obj.displayMyValues();
  return 0;
}

Output:- 
  	100
	A
```

## Address in C++

If we have a variable **`var`** in our program, **`&var`** will give us its address in the memory. For example,


```javascript
#include <iostream>
using namespace std;

int main()
{
    // declare variables
    int var1 = 3;
    int var2 = 24;
    int var3 = 17;

    // print address of var1
    cout << "Address of var1: "<< &var1 << endl;

    // print address of var2
    cout << "Address of var2: " << &var2 << endl;

    // print address of var3
    cout << "Address of var3: " << &var3 << endl;
}
```

Output
```javascript
Address of var1: 0x7fff5fbff8ac
Address of var2: 0x7fff5fbff8a8
Address of var3: 0x7fff5fbff8a4
```

![Pointer](https://prepinsta.com/wp-content/uploads/2023/02/Pointers-in-C.webp)
## C++ Pointers
A pointer is a variable that stores the memory address of an object. 

```javascript
int *pointVar;
```
Here, we have declared a pointer pointVar of the int type.


```javascript
int* pointVar; // preferred syntax
```

#### Assigning Addresses to Pointers

```javascript
int* pointVar, var;
var = 5;

// assign address of var to pointVar pointer
pointVar = &var;
```
Here, 5 is assigned to the variable **var.** And, the address of var is assigned to the pointVar pointer with the code **pointVar = &var.**


#### Get the Value from the Address Using Pointers

```javascript
int* pointVar, var;
var = 5;

// assign address of var to pointVar
pointVar = &var;

// access value pointed by pointVar
cout << *pointVar << endl;   // Output: 5
```

![Pointer](https://cdn.programiz.com/sites/tutorial2program/files/cpp-pointer-working.png)

## Virtual Function
A virtual function is a member function that is declared in the base class using the **keyword virtual** and is re-defined **(Overridden) in the derived class.** 

It tells the compiler to perform **late binding** where the compiler matches the object with the right called function and executes it during the **runtime.** This technique falls under Runtime Polymorphism.

Basically, a virtual function is used in the base class in order to ensure that the function is overridden. This especially applies to cases where a pointer of base class points to an object of a derived class.

For example, consider the code below:
```javascript
class Base {
   public:
    void print() {
        // code
    }
};

class Derived : public Base {
   public:
    void print() {
        // code
    }
};
```
Later, if we create a pointer of Base type to point to an object of **Derived** class and call the **`print()`** function, it calls the **`print()`** function of the **Base** class.

In other words, the member function of **Base is not overridden.**

```javascript
int main() {
    Derived derived1;
    Base* base1 = &derived1;

    // calls function of Base class
    base1->print();

    return 0;
}
```
In order to avoid this, we declare the print() function of the **Base** class as virtual by using the **virtual** keyword.

### Example 1: C++ Virtual Function
```javascript
#include <iostream>
using namespace std;

class Base {
   public:
    virtual void print() {
        cout << "Base Function" << endl;
    }
};

class Derived : public Base {
   public:
    void print() {
        cout << "Derived Function" << endl;
    }
};

int main() {
    Derived derived1;

    // pointer of Base type that points to derived1
    Base* base1 = &derived1;

    // calls member function of Derived class
    base1->print();

    return 0;
}
```
Output 
```javascript
Derived Function
```
![virtual function](https://cdn.programiz.com/sites/tutorial2program/files/cpp-virtual-function.png)


## Abastract Class
An abstract class is a class that is designed to be specifically used as a base class. An abstract class contains at least one pure virtual function.

[Notion Link](https://www.notion.so/konnectwithahsan/Code-with-Example-35a95615af184a80a405b6eab573e18c)

## Pure Virtual Function
A pure virtual function is a member function of base class whose only declaration is provided in base class and should be defined in derived class otherwise derived class also becomes abstract.

```javascript
class Shape {
    public:

      // creating a pure virtual function
      virtual void calculateArea() = 0;
};
```

### Example: C++ Abstract Class and Pure Virtual Function

```javascript
// C++ program to calculate the area of a square and a circle

#include <iostream>
using namespace std;

// Abstract class
class Shape {
   protected:
    float dimension;

   public:
    void getDimension() {
        cin >> dimension;
    }

    // pure virtual Function
    virtual float calculateArea() = 0;
};

// Derived class
class Square : public Shape {
   public:
    float calculateArea() {
        return dimension * dimension;
    }
};

// Derived class
class Circle : public Shape {
   public:
    float calculateArea() {
        return 3.14 * dimension * dimension;
    }
};

int main() {
    Square square;
    Circle circle;

    cout << "Enter the length of the square: ";
    square.getDimension();
    cout << "Area of square: " << square.calculateArea() << endl;

    cout << "\nEnter radius of the circle: ";
    circle.getDimension();
    cout << "Area of circle: " << circle.calculateArea() << endl;

    return 0;
}
```
Output
```javascript
Enter the length of the square: 4
Area of square: 16

Enter radius of the circle: 5
Area of circle: 78.5
```

## Abastract Class vs Interface


