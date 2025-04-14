# **Arrays or Lists in Python**

## **Time Complexity**

- **Lookup (access by index)**: **O(1)**  
    Arrays or lists provide **constant-time** access to elements by index.
    
- **Push (add an item to the end)**: **O(1)**  
    Adding an item to the end of the list is a constant-time operation, as long as there is space available.
    
- **Insert (add an item at any other position)**: **O(n)**  
    Inserting an element in the middle or at the beginning requires shifting all the subsequent elements, so the time complexity is linear in the size of the array.
    
- **Delete (remove an item)**: **O(n)**  
    Deleting an element from the middle or the beginning of the array requires shifting elements to fill the gap, making the time complexity linear.

---

## **What Are Arrays Good For?**

1. **Fast Lookup**:
    
    - Arrays or lists allow **constant-time** access to elements via indexing.
        
    - Example: `my_list[i]` where `i` is the index of the element.
        
2. **Fast Push/Pop (for the last item)**:
    
    - Adding or removing an element from the end of the list is done in **constant-time**.
        
    - Example: `my_list.append(x)` to add, and `my_list.pop()` to remove the last element.
        
3. **Ordered**:
    
    - Lists maintain the order of elements, making them useful when the sequence of data matters.

---

## **What Are Arrays Bad For?**

1. **Slow Inserts**:
    
    - Inserting elements in the middle or beginning requires shifting elements, resulting in **linear-time** complexity.
        
2. **Slow Deletes**:
    
    - Deleting an element from the middle or the beginning requires shifting elements to fill the gap, making it a **linear-time** operation.

---

## **Implementation Links**

1. **Arrays or Lists** - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/c651da944dc46d5321d4a69ea3a45c9c95fbeeb7/data-structures/arrays-or-lists/arrays-or-lists)
    
2. **Implementing an Array** - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/ff55371da841b5f52588fdfbb6bdde081efb7ebf/data-structures/arrays-or-lists/implementing-an-array)
    
3. **Reverse String** - [GitHub Link](https://github.com/grandeurkoe/data-structures-and-algorithms/tree/912024d64a32c74b25099a2d21ca255ed02c5e7e/data-structures/arrays-or-lists/reverse-a-string)