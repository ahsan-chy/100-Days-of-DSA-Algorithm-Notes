
# Link List

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

Create Pointer Object and Store Value in Node
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


## Singly Link List

#### Insert in Link List
- Insert at Start
- Insert at End  
- Insert at Middle
