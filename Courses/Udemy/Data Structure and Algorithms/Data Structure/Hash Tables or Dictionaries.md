# **Hash Tables (Dictionaries)**

In Python, **Hash Tables** are referred to as **Dictionaries**. A hash table is a data structure that stores data in key-value pairs, where each key is unique. The main advantage of hash tables is that they allow for efficient data retrieval and insertion operations.

## **How Hash Tables Work**

A **hash function** takes a key and returns a fixed-length value, often used as the address or index in the memory to store the associated value. This allows for very fast lookups, inserts, and deletions since these operations only require accessing a specific memory address.

### **Process:**

1. A key-value pair is given.
    
2. The **hash function** is applied to the key to generate a hash value of fixed length.
    
3. The hash value is mapped to a memory location.
    
4. The key-value pair is stored at that location.
    
5. During retrieval, the key is hashed again, and the corresponding value is fetched from the memory location.
    

### **Hash Collisions**

A **hash collision** occurs when two different keys generate the same hash value, resulting in both keys trying to access the same location in the table. This is a significant drawback because collisions slow down operations (lookup, insert, delete), especially when multiple keys map to the same address.

### **Collision Resolution Techniques:**

- **Chaining**: Store multiple key-value pairs at the same address, often in a linked list or another structure.
    
- **Open Addressing**: Find another available address within the hash table.
    
- **Cuckoo Hashing, Hopscotch Hashing, Coalesced Hashing**: These are other advanced techniques for managing hash collisions.
    

---

## **Time Complexity**

The time complexity for hash tables depends on the operation:

- **LOOKUP**: O(1) – Hash tables offer constant-time lookup if there are no collisions.
    
- **PUSH**: O(1) – Adding a new key-value pair is also constant-time unless a collision occurs.
    
- **INSERT**: O(1) – Insertion of a new key-value pair.
    
- **DELETE**: O(1) – Deleting a key-value pair is generally constant-time, assuming no major collisions.
    

However, in the worst-case scenario (e.g., when there are many collisions), the time complexity could degrade to O(n), but this is rare with a well-designed hash function.

---

## **Advantages of Hash Tables**

1. **Fast Lookup**: Hash tables are great for fast lookups because each key is mapped directly to a memory location.
    
2. **Fast Insertion**: Inserting key-value pairs is very efficient.
    
3. **Flexible Keys**: Hash tables allow a wide variety of keys (strings, integers, etc.) to be used, providing flexibility.
    

---

## **Disadvantages of Hash Tables**

1. **Unordered**: Hash tables do not store keys in any particular order. However, this is not a problem in Python, as dictionaries are ordered as of Python 3.7.
    
2. **Slow Key Iteration**: Iterating over keys is slower compared to other data structures like lists or arrays.
    

---

## **Example Implementations**

1. **First Recurring Character** – Find the first recurring character in a string using a hash table.
    
    - [First Recurring Character - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/85054015d27e987661f0c28e19df4cb374b9d9c9/data-structures/hash-tables-or-dictionaries/first-recurring-character)
        
2. **Hash Table or Dictionaries** – Learn about hash tables and their implementations in Python dictionaries.
    
    - [Hash Table or Dictionaries - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/7178cd324f55e2c084f43addae5d539609c66ac8/data-structures/hash-tables-or-dictionaries/hash-tables-or-dictionaries)
        
3. **Implementing a Hash Table** – A custom implementation of a hash table in Python.
    
    - [Implementing a Hash Table - GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/fa6cff6dc7e2c389b8b1ffa9732bc56360dfbb1e/data-structures/hash-tables-or-dictionaries/implementing-a-hash-table)
        

---

Hash tables are a powerful and efficient data structure widely used in programming for tasks that require quick lookups, inserts, and deletions.