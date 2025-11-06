

***

### Linked List Core Code (C++)

#### **Node Class**
```cpp
class Node {
public:
    int data;
    Node* next;

    Node(int value) {
        data = value;
        next = NULL;
    }
};
```

#### **Linked List Class**
```cpp
class List {
private:
    Node* head;
    Node* tail;
public:
    List() {
        head = NULL;
        tail = NULL;
    }
};
```

***

#### **push_front (Insert at Beginning)**
```cpp
void push_front(int value) {
    Node* newNode = new Node(value);
    if (head == NULL) {
        head = newNode;
        tail = newNode;
        return;
    }
    newNode->next = head;
    head = newNode;
}
```

#### **push_back (Insert at End)**
```cpp
void push_back(int value) {
    Node* newNode = new Node(value);
    if (head == NULL) {
        head = newNode;
        tail = newNode;
        return;
    }
    tail->next = newNode;
    tail = newNode;
}
```

#### **printList (Print All Elements)**
```cpp
void printList() {
    Node* temp = head;
    while (temp != NULL) {
        std::cout << temp->data << ' ';
        temp = temp->next;
    }
    std::cout << std::endl;
}
```

#### **pop_front (Remove First Element)**
```cpp
void pop_front() {
    if (head == NULL) {
        std::cout << "Linked List is empty" << std::endl;
        return;
    }
    Node* temp = head;
    head = head->next;
    delete temp;
}
```

#### **pop_back (Remove Last Element)**
```cpp
void pop_back() {
    if (head == NULL) {
        std::cout << "Linked List is empty" << std::endl;
        return;
    }
    Node* temp = head;
    while (temp->next != tail)
        temp = temp->next;
    delete tail;
    tail = temp;
    tail->next = NULL;
}
```

#### **insert (Insert at Specific Position)**
```cpp
void insert(int value, int position) {
    if (position < 0) {
        std::cout << "Invalid position" << std::endl;
        return;
    }
    if (position == 0) {
        push_front(value);
        return;
    }
    Node* temp = head;
    for (int i = 0; i < position - 1 && temp != NULL; ++i)
        temp = temp->next;
    if (temp == NULL) {
        std::cout << "Invalid position" << std::endl;
        return;
    }
    Node* newNode = new Node(value);
    newNode->next = temp->next;
    temp->next = newNode;
}
```

#### **search (Find Index of Element)**
```cpp
int search(int key) {
    Node* temp = head;
    int index = 0;
    while (temp != NULL) {
        if (temp->data == key)
            return index;
        temp = temp->next;
        ++index;
    }
    return -1;
}
```

***

### Explanations & Textual Concepts

- **Linked List** is a linear, dynamic data structure.
- Nodes contain *data* and a *pointer to next node*.
- Memory locations for nodes are non-contiguous, unlike arrays.
- Can only traverse in forward direction using the *head pointer*.
- *Tail pointer* is optional; it points to the last node.
- No direct indexing - iteration is necessary to access elements by position.
- Main operations:
    - **Insertion (push_front, push_back, insert at position)**
    - **Deletion (pop_front, pop_back)**
    - **Traversal (printList)**
    - **Search (search)**
- Time Complexity:
    - `push_front`, `push_back` (with tail): $$O(1)$$
    - `pop_front`: $$O(1)$$
    - `pop_back`, `insert(middle)`, `search`: $$O(n)$$
    - `printList`: $$O(n)$$
- Edge Cases:
    - Insert at 0 is equivalent to push_front.
    - Handle empty list in all functions.
    - Validate position for insert.

All code and textual explanations above are based **exactly** on the sequence, style, and implementation presented in the video. No extra content has been added.[1]

[11](https://www.placementpreparation.io/blog/best-youtube-channels-to-learn-data-structures-and-algorithms/)
