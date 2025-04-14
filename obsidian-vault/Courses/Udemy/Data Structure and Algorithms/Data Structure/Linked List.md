# **Linked List**

A **Linked List** is a linear data structure that consists of nodes, where each node contains a value and a reference (or pointer) to the next node in the sequence. Unlike arrays, the elements in a linked list are not stored in contiguous memory locations, but instead are linked together via pointers.

## **Structure of a Linked List**

- **Node**: Each element in a linked list is a node. Each node consists of:
    
    - A **value** or data field.
        
    - A **pointer** or reference to the next node in the list.
        
- **Head**: The first node in the linked list is called the **head**.
    
- **Tail**: The last node in the list is called the **tail**, and it points to **null**, indicating the end of the list.
    

A linked list is **null-terminated**, meaning that when we reach a node that points to null, we know the list has ended.

---

## **Time Complexity**

1. **PREPEND** (Insert at the beginning): O(1)
    
    - Inserting a new node at the beginning of the linked list only requires updating the pointer of the head.
        
2. **APPEND** (Insert at the end): O(1) (if we have a pointer to the tail)
    
    - Inserting at the end can be constant time if we have a reference to the tail, as we simply adjust the tail’s pointer.
        
3. **LOOKUP** (Search for a value): O(n)
    
    - To find a value in a linked list, we may need to traverse the entire list. Therefore, it takes linear time.
        
4. **INSERT** (Insert at a specific position): O(n)
    
    - To insert a node at a specific position, you need to traverse the list to reach that position.
        
5. **DELETE** (Delete a node): O(n)
    
    - Deleting a node requires finding the node first, which requires traversing the list.

---

## **Types of Linked Lists**

### **Singly Linked List**

- **Structure**: Each node has a pointer to the next node.
    
- **Traversal**: You can only traverse the list in one direction (from head to tail).
    
- **Memory**: A singly linked list uses less memory, as it only stores one pointer per node.

### **Doubly Linked List**

- **Structure**: Each node has two pointers:
    
    1. The **next** pointer points to the next node in the list.
        
    2. The **previous** pointer points to the previous node in the list.
        
- **Traversal**: You can traverse the list both forward (from head to tail) and backward (from tail to head).
    
- **Memory**: Doubly linked lists use more memory than singly linked lists, as they store two pointers per node. However, this allows for easier backward traversal.
    

---

## **Singly Linked List vs Doubly Linked List**

- **Singly Linked List**:
    
    - **Pros**: Requires less memory, faster for operations like insertion and deletion when compared to doubly linked lists, especially when you are only concerned with forward traversal.
        
    - **Cons**: Can only be traversed in one direction (head to tail). If you lose track of the head, all data can be lost.
        
- **Doubly Linked List**:
    
    - **Pros**: Allows for efficient traversal in both directions. Operations like insertions and deletions can be more efficient in some cases, as you can access both the previous and next nodes.
        
    - **Cons**: Uses more memory due to the extra pointer for the previous node. More complex to implement and maintain.

---

## **Implementation Links**

1. **Linked List** – A basic implementation of a linked list.
    
    - [Linked List - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/data-structures/linked-list/linked-list)
        
2. **Implementing a Singly Linked List** – A basic implementation of a singly linked list.
    
    - [Implementing a Singly Linked List - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/a2d8485399b1a3e5ef75095a6653c2cf9da9a137/data-structures/linked-list/implementing-a-singly-linked-list)
        
3. **Implementing a Doubly Linked List** – A basic implementation of a doubly linked list.
    
    - [Implementing a Doubly Linked List - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/8796780480e730d3b20250b7e4227ed583eec0ab/data-structures/linked-list/implementing-a-doubly-linked-list)
        
4. **Reversing a Singly Linked List** – How to reverse a singly linked list.
    
    - [Reversing a Singly Linked List - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/ef536f704cdf9fa16f54e52bad780769c8b871ac/data-structures/linked-list/reversing-a-singly-linked-list)

---

## **Summary**

Linked Lists are useful when you need efficient insertions and deletions, especially when the size of the data structure changes frequently. They allow for dynamic memory usage and can be modified without the need for resizing. However, they come with trade-offs such as slower lookups and the need for extra memory to store pointers.