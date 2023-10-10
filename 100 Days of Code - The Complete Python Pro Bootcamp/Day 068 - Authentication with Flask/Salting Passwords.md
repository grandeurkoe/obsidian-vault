# Salting Passwords

In Salting in addition to the password we generate a random set of characters which get combines with user's password. This combined password is then passed through the hash function to generate a hash value.

![[Pasted image 20231010121249.png|500]]

The bcrpyt hashing algorithm is an algorithm that is industry standard because it is extremely slow.

The bcrypt hashing algorithm has a concept called as salt rounds.

The more the salt rounds the saltier your password i.e., more secure.

Salt round 1

![[Pasted image 20231010121259.png|500]]

Salt round 2 using the same salt.

![[Pasted image 20231010121310.png|500]]

As computer get faster, all we need to do make our password more secure using bcrypt hashing algorithm is to add additional salt rounds.

So, in our database will store the randomly generated salt and the hash value after a fixed number of salting rounds.

![[Pasted image 20231010121323.png|500]]