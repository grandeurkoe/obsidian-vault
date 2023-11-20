# Linked List

Linked Lists are lists that are linked.

Linked List are made up of Nodes.

Each node consists of a Value and a Pointer that points to the next Node in the Linked List.

The first node in the Linked List is called the Head. Similarly, the last node is called the Tail.

The Tail node pointer points to Null, thus indicating the end of the Linked List.

Linked Lists are Null Terminated which signifies that this is the end of the Linked List.

Since we have to traverse the nodes if we want to search for a value, insert a value or delete a value. Thus, it has a time complexity of O(n).

## Time Complexity

1. PREPEND - O(1)
2. APPEND - O(1)
3. LOOKUP - O(n)
4. INSERT - O(n)
5. DELETE - O(n)

## Doubly Linked List

Doubly Linked List consists of two pointer -

1. The 'next' pointer that points to the next node in the Linked List.
2. The 'previous' pointer that points to the previous node in the Linked List.

In a doubly linked list, we can traverse the list both from the front and the back.

In a lookup operation, if we know whether the element to be looked up is closer to the front or the back, we can save a lot of time.

## Singly Linked List vs Doubly Linked List

The drawback of Doubly Linked List in comparison to Singly Linked List is that we have to store an extra 'previous' pointer.

Singly Linked Lists are used when there is a memory constraint.

If you lose track of the head in a Singly List, all the data in the Singly Linked List can be lost to memory.

Singly Linked List has a faster insert, deletion , searching, etc., in comparison to Doubly Linked List.

In a Doubly Linked List you can traverse from both the head and the tail.

Doubly Linked List is more complex than Singly Linked List.

## Implementation

1. Linked List - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/data-structures/linked-list/linked-list)
2. Implementing a Single Linked List - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/ddd45ffe40e2e229c13f576ba84bbb098ba77da4/data-structures/linked-list/implementing-a-singly-linked-list)
3. Implementing a Doubly Linked List - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/d7048c5693605eda2bf6e9d1739bea1dc7e7d160/data-structures/linked-list/implementing-a-doubly-linked-list)
4. Reversing a Singly Linked List - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/data-structures/linked-list/reversing-a-singly-linked-list)