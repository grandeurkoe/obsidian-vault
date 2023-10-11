# Relational Database Schemas: Primary and Foreign Keys

LEGO has licensed many hit franchises from Harry Potter to Marvel Super Heroes to many others. But which theme has the largest number of individual sets? Is it one of LEGO's own themes like Ninjago or Technic or is it a third party theme? Let's analyze LEGO's product lines in more detail!

## Number of Sets per LEGO Theme

To count the number of sets per Theme we can use the `.value_counts()` method on our `theme_id` column. But there's one problem:

![[2020-10-10_10-18-04-9bbb260d201de1b104afa814b9e6b1ca.png|500]]

We have no idea what our themes are actually called! 🤨 Ok, we can see that the theme with id 158 is the largest theme containing 753 individual sets, but what's that theme called? This is not very helpful. We need to find the names of the themes based on the `theme_id` from the `themes.csv` file.

## Working with a Relational Database

What is a database schema? A schema is just how the database is organized. Many relational databases, such as our LEGO data, is split into individual tables. We have separate tables for the colors, the sets and the themes. With a relational database, the tables are linked to each other through their keys.

### Understand the theme.csv file

The themes.csv file has the actual theme names. How is this table linked to the others tables? Well, the sets .csv has `theme_ids` which match the `id` column in the themes.csv.

This means that the `theme_id` is the **foreign key** inside the sets.csv. Many different sets can be part of the same theme. But _inside_ the themes.csv, each `theme_id`, which is just called `id` is unique. This uniqueness makes the `id` column the **primary key** inside the themes.csv. To see this in action, explore the themes.csv.

Looking at the first 5 rows, we see the column names. Each value in the id column is unique (this is the primary key for the themes table). The theme names are not unique. If we search for the name "Star Wars", we see that 4 different ids correspond to that name.

![[2020-10-10_10-20-17-7a41efe0fd36de47692c93fd25cac833.png|500]]

Why would Star Wars have so many different themes? We can check which products corresponded to those themes in the sets.csv:

![[2020-10-10_10-20-26-e9094eb0b1ab6154493c48b700afd79b 1.png|500]]

Star Wars is a really long-running franchise. Theme number 18 was running from 2000 to 2002 and seems to be comprised of several of the show's characters. What about, say theme 209?

![[2020-10-10_10-20-26-e9094eb0b1ab6154493c48b700afd79b.png|500]]

Here we see that all of the Star Wars Advent Calendars share the same `theme_id`. That makes sense.

![[2020-10-10_10-20-45-635c014ae055a295c7e605acb5cd3bc1.jpg|500]]