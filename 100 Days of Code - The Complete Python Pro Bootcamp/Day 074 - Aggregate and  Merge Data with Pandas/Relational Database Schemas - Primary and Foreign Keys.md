# Relational Database Schemas: Primary and Foreign Keys

LEGO has licensed many hit franchises from Harry Potter to Marvel Super Heroes to many others. But which theme has the largest number of individual sets? Is it one of LEGO's own themes like Ninjago or Technic or is it a third party theme? Let's analyze LEGO's product lines in more detail!

## Number of Sets per LEGO Theme

To count the number of sets per Theme we can use the `.value_counts()` method on our `theme_id` column. But there's one problem:

![[2020-10-10_10-18-04-9bbb260d201de1b104afa814b9e6b1ca.png|500]]

We have no idea what our themes are actually called! 🤨 Ok, we can see that the theme with id 158 is the largest theme containing 753 individual sets, but what's that theme called? This is not very helpful. We need to find the names of the themes based on the `theme_id` from the `themes.csv` file.

## Working with a Relational Database

What is a database schema? A schema is just how the database is organized. Many relational databases, such as our LEGO data, is split into individual tables. We have separate tables for the colors, the sets and the themes. With a relational database, the tables are linked to each other through their keys.

