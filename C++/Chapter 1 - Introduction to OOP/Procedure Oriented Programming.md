In the procedure oriented approach, the problem is viewed as the sequence of things to be done such as reading, calculating and printing.

The primary focus is on functions. 

The technique of hierarchical decomposition has been used to specify the tasks to be completed for solving a problem.

A typical structure for procedural programming is shown in the figure below. 

![[Pasted image 20240506200207.png|500]]

Procedure oriented programming basically consists of writing a list of instructions for the computer to follow, and organizing these instructions into groups known as functions. We normally use flowcharts to organize these actions and represent the flow of control from one action to another.

In a multi-function program, many important data items are placed as global so that they may be accessed by all the functions. Each function may have its own local data. Global data are more vulnerable to an inadvertent change by a function. In a large program it is very difficult to identify what data is used by which function. In case we need to revise an external data structure, we also need to revise all functions that access the data. This provides an opportunity for bugs to creep in.

Another serious drawback with the procedural approach is that we do not model real world problems very well. This is because functions are action-oriented and do not really corresponding to the element of the problem.

**Characteristics of Procedure Oriented Programming**

1. Emphasis is on doing things (algorithms).
2. Large programs are divided into smaller programs known as functions.
3. Most of the functions share global data.
4. Data move openly around the system from function to function.
5. Functions transform data from one form to another.
6. Employs top-down approach in program design.