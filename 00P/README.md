
# OOP

Table Of Content
- Address in C++
- Pointer
- Abstraction
- Virtual Function 
- Pure Virtual Function
- Abastract Class
- Abstract Class - Interface
- Compiletime Polymorphism vs Runtime Polymorphism
- Struct vs Class
- This
- Constructor
    - Default Constructor
    - parameterized Constructor
    - Copy Constructor
- Friend Function
- Friend Class

## Address in C++

If we have a variable **`var`** in our program, **`&var`** will give us its address in the memory. For example,


```c++
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
```c++
Address of var1: 0x7fff5fbff8ac
Address of var2: 0x7fff5fbff8a8
Address of var3: 0x7fff5fbff8a4
```

![Pointer](https://prepinsta.com/wp-content/uploads/2023/02/Pointers-in-C.webp)
## C++ Pointers
A pointer is a variable that stores the memory address of an object. 

```c++
int *pointVar;
```
Here, we have declared a pointer pointVar of the int type.


```c++
int* pointVar; // preferred syntax
```

#### Assigning Addresses to Pointers

```c++
int* pointVar, var;
var = 5;

// assign address of var to pointVar pointer
pointVar = &var;
```
Here, 5 is assigned to the variable **var.** And, the address of var is assigned to the pointVar pointer with the code **pointVar = &var.**


#### Get the Value from the Address Using Pointers

```c++
int* pointVar, var;
var = 5;

// assign address of var to pointVar
pointVar = &var;

// access value pointed by pointVar
cout << *pointVar << endl;   // Output: 5
```

![Pointer](https://cdn.programiz.com/sites/tutorial2program/files/cpp-pointer-working.png)


## Abstraction

Abstraction is the concept of object-oriented programming that “Shows” only essential attributes and “Hides” unnecessary information.

**Example:** 
- Consider a real-life example of a man driving a car. The man only knows that pressing the accelerators will increase the speed of car or applying brakes will stop the car but he does not know about how on pressing the accelerator the speed is actually increasing, he does not know about the inner mechanism of the car or the implementation of accelerator, brakes etc in the car. This is what abstraction is.
- A.C 
- Mobile 





## Virtual Function
A virtual function is a member function that is declared in the base class using the **keyword virtual** and is re-defined **(Overridden) in the derived class.** 

It tells the compiler to perform **late binding** where the compiler matches the object with the right called function and executes it during the **runtime.** This technique falls under Runtime Polymorphism.

Basically, a virtual function is used in the base class in order to ensure that the function is overridden. This especially applies to cases where a pointer of base class points to an object of a derived class.

For example, consider the code below:
```c++
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

```c++
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
```c++
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
```c++
Derived Function
```
![virtual function](https://cdn.programiz.com/sites/tutorial2program/files/cpp-virtual-function.png)


#### Amir Code Example 
- Virtual Function
- Create **Pointer object** 
- Access Pointer object

**Without Virtual Function** It will display parent class function every time. 

```c++
#include <iostream>

using namespace std;

class Shape {
    public:
     void describeSelf () {
        cout << "I am Shape" << endl;
    }
};
class Circle: public Shape {
    public:
    void describeSelf () {
        cout << "I am Circle" << endl;
    }
};
class Rectangle: public Shape {
    public:
    void describeSelf () {
        cout << "I am Rectangle" << endl;
    }
};
class Triangle: public Shape  {
    public:
    void describeSelf () {
        cout << "I am Triangle" << endl;
    }
};
int main() {
    Shape *s = new Shape();
    s->describeSelf(); // I am Shape
    s = new Circle();
    s->describeSelf(); // I am Shape
    s = new Rectangle();
    s->describeSelf(); // I am Shape
    s = new Triangle();
    s->describeSelf(); // I am Shape
    return 0;
}
```

By Using **Virtual keyword** in Parent Class
```c++
// Online C++ compiler to run C++ program online
#include <iostream>

using namespace std;

class Shape {
    public:
    virtual void describeSelf () {
        cout << "I am Shape" << endl;
    }
};
class Circle: public Shape {
    public:
    void describeSelf () {
        cout << "I am Circle" << endl;
    }
};
class Rectangle: public Shape {
    public:
    void describeSelf () {
        cout << "I am Rectangle" << endl;
    }
};
class Triangle: public Shape  {
    public:
    void describeSelf () {
        cout << "I am Triangle" << endl;
    }
};
int main() {
    Shape *s = new Shape();
    s->describeSelf(); // I am Shape
    s = new Circle();
    s->describeSelf(); // I am Circle
    s = new Rectangle();
    s->describeSelf(); // I am Rectangle
    s = new Triangle();
    s->describeSelf(); // I am Triangle
    return 0;
}
```



## Pure Virtual Function
A pure virtual function is a member function of base class whose only declaration is provided in base class and should be defined in derived class otherwise derived class also becomes abstract.

```c++
class Shape {
    public:

      // creating a pure virtual function
      virtual void calculateArea() = 0;
};
```

### Example: C++ Abstract Class and Pure Virtual Function

```c++
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
```c++
Enter the length of the square: 4
Area of square: 16

Enter radius of the circle: 5
Area of circle: 78.5
```


## Abastract Class

An abstract class is a class that is designed to be specifically used as a base class. An abstract class contains at least one pure virtual function.

```c++
#include <bits/stdc++.h>

using namespace std;

class person
{
  string p_id;
  public:
  virtual void get_info()=0; //declaring person as abstract class
  virtual void show()=0;
};

class student:public person
{
  string name;
  int roll_no;
  public:

  /*overriding the pure virtual function declared in base class otherwise, this class will become an abstract one and then objects cannot be created for the same*/

    void get_info()
    {
      cout<<"Enter name of the student "<<endl;
      cin>>name;
      cout<<"Enter roll number of the student "<<endl;
      cin>>roll_no;
    }
   void show()
   {
     cout<<"Name : "<<name<<" Roll number: "<<roll_no<<endl;
   }
};

int main()
{
  person *p = new student;  
  p->get_info();
  p->show();
  return 0;
}
```

[Detail **Abstraction** Notion Link](https://www.notion.so/konnectwithahsan/Code-with-Example-35a95615af184a80a405b6eab573e18c)


## **Abstract Class** vs **Interface**



### How We can achive **Compiletime Polymorphism** 
- Early Binding 
- Static Binding


### How We can achive **Runtime Polymorphism** 
- Late Binding
- Dynamic Binding 





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

```c++
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

## Constructor
A constructor is a special type of member function that is invoked automatically when an object is created.

- In C++, a constructor has the same name as that of the class and **it does not have a return type.** For example,

```C++
class  Wall {
  public:
    
    Wall() {  // declare constructor
      // code
    }
};
```
- It is use to initialize the object of its class.

More charactristics of Constructor:
- It should be declared in **Public Section of class.**
- It can have Default Arguments
- We can't refer to their address





### Default Constructor
A constructor with no parameters is known as a default constructor. In the example above, Wall() is a default constructor.


```c++
// declare a class
class  Wall {
  private:
    double length;

  public:
    // default constructor to initialize variable
    Wall() {
      length = 5.5;
      cout << "Creating a wall." << endl;
      cout << "Length = " << length << endl;
    }
};

int main() {
  Wall wall1;
  return 0;
}
```
Output
```c++
Creating a Wall
Length = 5.5
```

### Parameterized Constructor
Constructor with parameters is known as a parameterized constructor. This is the preferred method to initialize member data.

```C++
// C++ program to calculate the area of a wall

#include <iostream>
using namespace std;

// declare a class
class Wall {
  private:
    double length;
    double height;

  public:
    // parameterized constructor to initialize variables
    Wall(double len, double hgt) {
      length = len;
      height = hgt;
    }

    double calculateArea() {
      return length * height;
    }
};

int main() {
  // create object and initialize data members
  Wall wall1(10.5, 8.6);
  Wall wall2(8.5, 6.3);

  cout << "Area of Wall 1: " << wall1.calculateArea() << endl;
  cout << "Area of Wall 2: " << wall2.calculateArea();

  return 0;
}
```
Output:
```c++
Area of Wall 1: 90.3
Area of Wall 2: 53.55
```

### Copy Constructor




##  Friend Function

##  Friend Class