---
title: Data Trees
---

# {{ $page.title }}

Data trees are at the core of Grasshopper's functionality and understanding them is of key importance for us. In this chapter you will learn:

- What are data trees?
- What do data trees _mean_?
- How does Grasshopper process data trees as inputs?
- Data Tree Inspection tools
  - ParamViewer
  - Panel
- Data Tree basic operations
  - Flatten
  - Graft
  - Simplify
  - Weave
  - Sift
- Data Tree selection
  - Relative Item
  - Split Tree
  - Relative Items
- Cross-reference

## What are data trees ?

Data Trees are the way Grasshopper organizes data internally, wether it's numbers, lines, circles, meshes, surfaces or any combination of the latter. In that sense, we understand a Data Tree as a way to organize entities into different categories.

> As you might already know, branches are named using curly brackets `{}` while branch indexes are named using square brackets `[]`. Multiple branch levels are separated using `;`.
> i.e.: The first item in the first branch of a four level data tree is specified as `{0;0;0;0}[0]`.

In the simplest case, a 1-dimensional data tree is a list of data at branch `{0}` with any number of items `[n]`, this would be the equivalent of one column in an excel spreadsheet table. Consider the following example:

<!-- TODO: Insert example! -->

The following level of complexity would be a 2-dimensional data tree, with $n$ number of branches with $m$ number of items each (`{n}[m]`). This would be equivalent to an excel spreadsheet, each branch representing a column, and each item representing a row in that specific column.

<!-- TODO: Insert example! -->

3-dimensional data trees are the last data tree depth that can be easily visualized. It is comprised of $n;m$ branches with $o$ number of items each (`{n;m}[o]`). Using the same analogy, this would be equivalent to an excel spreadsheet with multiple tables or sheets. Consider the following example:

<!-- TODO: Insert example! -->

1-dimensional and 2-dimensional data trees are the easiest to use and combine, but they have limited possibilities to represent complex data relations. As your grasshopper definitions grow, you will start dealing with _n-dimensional_ data trees more often.

## Structure = Meaning

As you may have noticed, the examples in the previous section were all based on _categorical data_. This was a decision we took conciously, instead of representing the examples with geometric entities, since we wanted to emphathise the fact that the underlying data structure of a tree has actual meaning.

Lets have a look at the last example from the previous section:

> The data tree is divided in 3 levels, each containing a list of values:
>
> - `{0;n;n}` Plant
>   - `{0;0;n}` Vegetable
>     - `{0;0;0}` Product
>     - `{0;0;1}` Price
>     - `{0;0;2}` Color
>   - `{0;1;n}` Fruit
>     - `{0;1;0}` Product
>     - `{0;1;1}` Price
>     - `{0;1;2}` Color
> - `{1;n;n}` Animal
>   - `{1;0;n}` Meat
>     - `{1;0;0}` Product
>     - `{1;0;1}` Price
>     - `{1;0;2}` Color
>   - `{1;1;n}` Dairy
>     - `{1;1;0}` Product
>     - `{1;1;1}` Price
>     - `{1;1;2}` Color

In this 4-dimensionaL tree, every tree level has a _meaning_ or, in other words, they represent distinct characteristic of the data it contains:

- The first level divides the data in Plant or Animal based products.
- The second level divides each of those main categories into their own unique subcategories
- The third level represents the different types of values we have fore each subcategory:
  - Product name
  - Product price
  - Product color

## Advanced Data Trees

## Advanced selection

## Structure relationships

## Advanced tree editing
