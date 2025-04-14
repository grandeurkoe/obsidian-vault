# Analysis by Programming Language

In order to look at the number of entries and the number of posts by programming language, we need to make use of the `.groupby()` method. The key is combining `.groupby()` with the TAG column, which holds as our categories (the names of the programming languages).

If we `.sum()` the number of posts then we can see how many posts each programming language had since the creation of Stack Overflow.

![[2020-09-23_11-47-22-ce767dc3efa884429a71bb35e652a131.png|500]]

If we `.count()` the entries in each column, we can see how many months of entries exist per programming language.

![[2020-09-23_11-47-32-a4950dc10e6c67b4556545955537ba86.png|500]]