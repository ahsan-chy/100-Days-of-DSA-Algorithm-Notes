
# Link List

![Link List](https://media.geeksforgeeks.org/wp-content/uploads/20220816144425/LLdrawio.png)

Link List Syntex:

![Link List](https://user-images.githubusercontent.com/85479513/228701009-957ac27c-c4c6-4415-a890-dcf401bf07de.png)

```javascript
class Node {
	public:
	int data;
	Node* next;

	Node(int data){					//- This is Constructor 
		this-> data = data;
		this-> next = NULL;
	}
};
```

```javascript
// - Create Nodes 
	Node* head = NULL;
	Node* curr = new Node(10);
	head = curr;
	Node* second = new Node(35);
	curr -> next = second;

  cout << head -> data << endl;
  cout << second -> data << endl;
```

#### Display LinkList Data Using loop

```c++
  while (head != NULL) {
    cout << head->data <<endl;
    head = head->next;
  }
```







### Example:

```javascript
#include <iostream>

using namespace std;

class Node {
public:
    int data;
    Node* next;

    Node(int val) {
        data = val;
        next = NULL;
    }
};

int main() {
    // Create three nodes
    Node* head = new Node(5);
    Node* second = new Node(10);
    Node* third = new Node(15);

    // Link the nodes together
    head->next = second;
    second->next = third;

    // Display the pointers
    cout << "Head points to address: " << head << endl;
    cout << "Second points to address: " << second << endl;
    cout << "Third points to address: " << third << endl;

    return 0;
}

```
### Explanation 

Class
```javascript
class Node {
public:
    int data;
    Node* next;

    Node(int val) {
        data = val;
        next = NULL;
    }
};
```

Create Nodes and Store Value in Node
```javascript
  // Create three nodes
    Node* head = new Node(5);
    Node* second = new Node(10);
    Node* third = new Node(15);

```
Link the nodes together
```javascript
    head->next = second;
    second->next = third;
```

Display the pointers
```javascript
 // Display the pointers
    cout << "Head points to address: " << head << endl;
    cout << "Second points to address: " << second << endl;
    cout << "Third points to address: " << third << endl;
```

#### [Programize Link List](https://www.programiz.com/dsa/linked-list)


## Singly Link List

![Singly Link List](https://simplesnippets.tech/wp-content/uploads/2019/06/singly-linked-list-data-structure.jpg)

#### Insert in Link List
- Insert at Start
- Insert at End  
- Insert at Middle


```c++

```

```c++

```