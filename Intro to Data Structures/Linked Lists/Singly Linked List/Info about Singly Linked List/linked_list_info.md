# Singly Linked List

A **Singly Linked List** is a fundamental data structure in Computer Science that consists of a sequence of elements, called **nodes**, where each node stores data and a reference (or pointer) to the next node in the sequence. Unlike arrays, Singly Linked Lists do not store elements in contiguous memory locations, making them dynamic and flexible in terms of memory usage.

---

## Structure of a Singly Linked List

Each node in a singly linked list typically has two components:

1. **Data**: The value or information the node contains.
2. **Next (Pointer)**: A reference to the next node in the sequence. The last node in the list has the `next` pointer set to `null` (or `None` in Python), indicating the end of the list.

---

## Key Concepts

1. **Head**: The starting node of the list. If the list is empty, the head is `null` or `None`.
2. **Traversal**: To access or process elements, you must traverse the list starting from the head, following the `next` pointers until you reach the end.
3. **Dynamic Size**: Singly linked lists can grow or shrink in size dynamically, as memory allocation happens on a per-node basis.

---

## Advantages of Singly Linked Lists

1. **Dynamic Memory Usage**: Unlike arrays, there is no need to define the size of the list in advance.
2. **Efficient Insertions and Deletions**: Adding or removing elements (especially at the beginning) is efficient, with O(1) time complexity, as no shifting of elements is required.

---

## Disadvantages of Singly Linked Lists

1. **Sequential Access**: Accessing an element requires traversing from the head, leading to \(O(n)\) time complexity for search or access.
2. **Extra Memory for Pointers**: Each node requires additional memory for storing the pointer.

---

## Basic Operations

1. **Insertion**:

    - **At the beginning**: Create a new node, set its `next` pointer to the current head, and update the head to the new node.
    - **At the end**: Traverse to the last node, set its `next` pointer to the new node.
    - **At a specific position**: Traverse to the desired position and adjust pointers accordingly.

2. **Deletion**:

    - **At the beginning**: Update the head to point to the second node.
    - **At the end**: Traverse to the second last node and set its `next` to `null`.
    - **At a specific position**: Traverse to the node before the one to delete and adjust pointers.

3. **Traversal**:
   Start at the head and follow the `next` pointers while processing the data of each node.

4. **Search**:
   Traverse the list to find an element that matches a given value.

---

## Example Implementation (Python)

```python
class Node:
    def __init__(self, data):
        self.data = data  # Store data
        self.next = None  # Pointer to the next node

class SinglyLinkedList:
    def __init__(self):
        self.head = None  # Initialize the head

    def insert_at_beginning(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node

    def insert_at_end(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        current = self.head
        while current.next:
            current = current.next
        current.next = new_node

    def traverse(self):
        current = self.head
        while current:
            print(current.data, end=" -> ")
            current = current.next
        print("None")

# Example Usage
sll = SinglyLinkedList()
sll.insert_at_beginning(10)
sll.insert_at_beginning(20)
sll.insert_at_end(30)
sll.traverse()
```

````

**Output**:

```
20 -> 10 -> 30 -> None
```

---

## Applications of Singly Linked Lists

1. **Dynamic memory allocation**: Used in scenarios where the size of the dataset changes dynamically.
2. **Stacks and Queues**: Singly linked lists are a common choice for implementing stacks and queues.
3. **Adjacency lists in Graphs**: Representing graph edges efficiently.
4. **Polynomial representation**: Used to represent polynomials where each term is a node.

---

Understanding singly linked lists is foundational to learning more complex data structures like doubly linked lists, circular linked lists, and beyond.

```

```
````
