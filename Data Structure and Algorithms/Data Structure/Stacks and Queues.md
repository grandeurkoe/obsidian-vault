# Stacks and Queues

Stacks and Queues are what we call Linear Data Structure.

Linear Data Structure allows us to traverse data elements sequentially.

Stacks and Queues are only used to run commands like push, pop, peek i.e. commands that deal with data element at the beginning and the end.

Stacks and Queues are higher level data structure, which means that they are built on top of lower level data structure like Arrays and Linked Lists.

Sometimes it is useful to limit the number of operations that can be performed on a data structure.

## Stacks

Stacks follow Last In First Out(LIFO).

Most programming languages are built based on the concept of Stacks.

The process of undoing changes also makes use of Stacks.

Stacks can be built using either Arrays or Linked Lists.

Since Arrays are stored in the memory right next to each other, it is faster to access array elements. However, Linked List elements are scattered all over memory and thus accessing them takes a longer time.

The limitation of using Array to build stacks is that they can only hold so many elements before they run out of memory at which point we will have to create another array to hold the extra elements.

### Time Complexity

1. LOOKUP - O(n).
2. POP - O(1).
3. PUSH - O(1).
4. PEEK - O(1) - To get the first element of the stack or the element at the top of the stack.

### Implementation

1. Implementing a Stack using Array - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/8accd2356b1eb33a3a73913aeb1e9bb63c4918d0/data-structures/stacks-and-queues/implementing-a-stack-using-array)
2. Implementing a Stack using Linked List - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/data-structures/stacks-and-queues/implementing-a-stack-using-linked-list)

## Queues

Queues follow First In First Out(FIFO).

Arrays are not used to build queues because they are inefficient.

Queues are usually built using Linked Lists.

We don't use Arrays to build Queues because we remove the first element in the array then each subsequent element would have to be shifted which take a long time(O(n)).

In contrast, the time complexity of removing the first element in Linked List is O(1).

### Time Complexity

1. LOOKUP - O(n).
2. ENQUEUE - O(1).
3. DEQUEUE - O(1).
4. PEEK - O(1).

### Implementation

Implementing a Queue using Linked List - [Github Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/4f0a0409009e63683acc86bdb94471532b085e7e/data-structures/stacks-and-queues/implementing-a-queue-using-linked-list)

## What are Stacks + Queues good for?

1. Fast operations.
2. Fast peek.
3. Ordered.

## What are Stacks + Queues bad for?

1. Slow lookup.