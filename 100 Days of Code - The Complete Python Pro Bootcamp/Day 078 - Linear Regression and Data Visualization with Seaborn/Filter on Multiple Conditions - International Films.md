# Filter on Multiple Conditions: International Films

So far, we've created subsets for our DataFrames based on a single condition. But what if we want to select our data based on more than one condition? For example, which films made money internationally (i.e., `data.USD_Worldwide_Gross != 0`), but had zero box office revenue in the United States (i.e., `data.USD_Domestic_Gross == 0`)? 

How would we create a filter for these two conditions? One approach is to use the `.loc[]` property combined with the [bitwise and](https://docs.python.org/3.4/library/operator.html#mapping-operators-to-functions) `&` operator.
