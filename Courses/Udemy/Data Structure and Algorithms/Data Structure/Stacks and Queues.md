# **Stacks and Queues**

**Stacks** and **Queues** are linear data structures that are built to handle data in a specific order. These data structures are commonly used to manage data where operations need to follow strict rules regarding access to elements (either the beginning or the end of the structure). Both stacks and queues can be implemented using arrays or linked lists and are widely used in various applications such as undo operations, scheduling tasks, or managing resources.

## **What are Linear Data Structures?**

Linear data structures allow elements to be accessed sequentially, one after the other. Both stacks and queues operate in a linear fashion, but they differ in the specific order in which elements are added or removed.

---

## **Stacks**

Stacks follow the **Last In, First Out (LIFO)** principle, meaning that the last element added to the stack is the first one to be removed.

- **Use Cases**:
    
    - Undo functionality in applications (like text editors).
        
    - Function call management (e.g., call stack in programming languages).
        
    - Browsing history in web browsers.
        

### **Operations on a Stack**:

1. **PUSH**: Add an element to the top of the stack.
    
2. **POP**: Remove the element from the top of the stack.
    
3. **PEEK**: Look at the top element without removing it.
    
4. **LOOKUP**: Search for an element (O(n) complexity).
    

### **Time Complexity**:

- **LOOKUP**: O(n)
    
- **POP**: O(1)
    
- **PUSH**: O(1)
    
- **PEEK**: O(1)
    

### **Implementation**:

1. **Implementing a Stack using an Array**:
    
    - [GitHub Link: Implementing a Stack using Array](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/82453132e845d75608172b124978b20bab83517c/data-structures/stacks-and-queues/implementing-a-stack-using-array)
        
2. **Implementing a Stack using Linked List**:
    
    - [GitHub Link: Implementing a Stack using Linked List](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/89e2a794d97c1cfd1a8bdedbb6a63722c0bc7c84/data-structures/stacks-and-queues/implementing-a-stack-using-linked-list)
        

---

## **Queues**

Queues follow the **First In, First Out (FIFO)** principle, meaning that the first element added to the queue is the first one to be removed.

- **Use Cases**:
    
    - Task scheduling in operating systems (e.g., CPU scheduling).
        
    - Message queue systems.
        
    - Print job management in printers.
        

### **Operations on a Queue**:

1. **ENQUEUE**: Add an element to the end of the queue.
    
2. **DEQUEUE**: Remove an element from the front of the queue.
    
3. **PEEK**: Look at the front element without removing it.
    
4. **LOOKUP**: Search for an element (O(n) complexity).
    

### **Time Complexity**:

- **LOOKUP**: O(n)
    
- **ENQUEUE**: O(1)
    
- **DEQUEUE**: O(1)
    
- **PEEK**: O(1)
    

### **Implementation**:

1. **Implementing a Queue using Linked List**:
    
    - [GitHub Link: Implementing a Queue using Linked List](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/9eae60e307700b04dde6fe551c7b2e9165d44258/data-structures/stacks-and-queues/implementing-a-queue-using-linked-list)
        

---

## **Advantages and Disadvantages of Stacks and Queues**

### **Advantages**:

1. **Fast Operations**: Both stacks and queues provide fast operations such as **PUSH**, **POP**, **ENQUEUE**, and **DEQUEUE** (usually O(1)).
    
2. **Fast Peek**: You can quickly check the top element of a stack or the front element of a queue without removing them.
    
3. **Ordered**: Both stacks and queues are ordered structures, meaning elements are processed in a specific sequence.
    

### **Disadvantages**:

1. **Slow Lookup**: Since elements are added or removed from one end (or both ends), searching for an element in a stack or queue takes linear time, O(n), since traversal is required.
    

---

## **Conclusion**

Stacks and queues are foundational data structures that offer efficient operations in specific scenarios. While stacks are great for handling data in a LIFO manner, and queues are ideal for FIFO operations, both can be used in a variety of applications. Understanding their properties, strengths, and limitations is essential for selecting the right data structure for a given problem.