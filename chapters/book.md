---
title: Messy Wires
subtitle: Creating successful visual scripts using Grasshopper
author:
    - Alan Rynne
    - Noelia Rodriguez
---

# Introduction

During the last 10 years, visual programming tools have become mainstream in many industries, transforming the way we design in the process.
This new tools allow architects and designers to create unprecedented designs, introducing unique features that have become the trademark image of many successfull architects.

However, these added capabilities usually come at a price: these higher level programming environments are the result of bringing coding concepts into the design space and, as such, benefitting from them requires a broad understanding of the underlying logic these programs follow.

In this book, we will cover some of this concepts using Rhinoceros Grasshopper, a very popular visual programming software, that is widely used in many industries.

It's title, *Messy Wires*, makes allusion to one of the main problems when creating successfull visual programming scripts at a professional level: *code clarity*, wich we will explain in more detail in [INSERT_REFERENCE].

We will start by understanding Grasshopper *Data Trees*, explaining the logic behind how they work, and how to properlly use them to introduce complexity in our designs while at keeping the size of our scripts manageable.

We will also cover some visual programming good practices, such as grouping, naming conventions, structuring and ordering scripts and some concepts directly inherited from programing, such as DRY (Don't Repeat Yourself).

More...

* Scripting
* BIM Connection
* Teamwork

## How to use this book

This book contains multiple example files, that will be uploaded at the books own GitHub Repository.

Througout the book, you will find BIDI codes that will link to the apropriate files for each section.

Since we will be using Grasshopper as our main tool, most of the files will be saved in `.ghx` format, which is 'friendlier' to 'git', the version control software we use (and love!).

## Who is this book aimed for

This book is aimed at designers, engineers, architects and any other design professionals who are already familiar with the basic use of Grasshopper but want to be able to use it proficiently on their daily workflow.

If you are not familiar with the use of Grasshopper as a design tool, we recommend you to check out this incredible resources:

* Grasshopper website
* Grasshopper intro courses by David Rutten
* Grasshopper advanced courses by David Rutten
* ThinkParametric

# Software requirements

* Rhinoceros 6 and Grasshopper.
* Archicad 21

# Nodes

Visual programming software, such as Grasshopper, is amost always based on the concept of ***nodes***, wich can be connected in a chain like manner to create complex interactions between them.

Consider the following grasshopper nodes:

:::{#fig:ghComponents}

![Inputless component](){#fig:Code1}
![Outputless component](){#fig:Code2}
![Component with input and output](){#fig:Code3}

:::

Grasshopper components can have any number of inputs and outputs, including none, as can be seen in [@fig:ghComponents].

# Basic Data Trees

Data trees are at the core of Grasshopper's functionality and understanding them is of key importance for us. In this chapter you will learn:

* What are data trees?
* What do data trees *mean*?
* How does Grasshopper process data trees as inputs?
* Data Tree Inspection tools
    * ParamViewer
    * Panel
* Data Tree basic operations
    * Flatten
    * Graft
    * Simplify
    * Weave
    * Sift
* Data Tree selection
    * Relative Item
    * Split Tree
    * Relative Items
* Cross-reference

## What are data trees?

Data Trees are the way Grasshopper organizes data internally, wether it's numbers, lines, circles, meshes, surfaces or any combination of the latter. In that sense, we understand a Data Tree as a way to organize entities into different categories.

> As you might already know, branches are named using curly brackets `{}` while branch indexes are named using square brackets `[]`. Multiple branch levels are separated using `;`.
> i.e.: The first item in the first branch of a four level data tree is specified as `{0;0;0;0}[0]`.

In the simplest case, a 1-dimensional data tree is a list of data at branch `{0}` with any number of items `[n]`, this would be the equivalent of one column in an excel spreadsheet table. Consider the following example:

<!-- TODO: Insert example! -->

The following level of complexity would be a 2-dimensional data tree, with $n$ number of branches with $m$ number of items each (`{n}[m]`). This would be equivalent to an excel spreadsheet, each branch representing a column, and each item representing a row in that specific column.

<!-- TODO: Insert example! -->

3-dimensional data trees are the last data tree depth that can be easily visualized. It is comprised of $n;m$ branches with $o$ number of items each (`{n;m}[o]`). Using the same analogy, this would be equivalent to an excel spreadsheet with multiple tables or sheets. Consider the following example:

<!-- TODO: Insert example! -->

1-dimensional and 2-dimensional data trees are the easiest to use and combine, but they have limited possibilities to represent complex data relations. As your grasshopper definitions grow, you will start dealing with *n-dimensional* data trees more often.

## Structure = Meaning

As you may have noticed, the examples in the previous section were all based on *categorical data*. This was a decision we took conciously, instead of representing the examples with geometric entities, since we wanted to emphathise the fact that the underlying data structure of a tree has actual meaning.

Lets have a look at the last example from the previous section:

> The data tree is divided in 3 levels, each containing a list of values:
>
> * `{0;n;n}` Plant
>     * `{0;0;n}` Vegetable
>         * `{0;0;0}` Product
>         * `{0;0;1}` Price
>         * `{0;0;2}` Color
>     * `{0;1;n}` Fruit
>         * `{0;1;0}` Product
>         * `{0;1;1}` Price
>         * `{0;1;2}` Color
> * `{1;n;n}` Animal
>     * `{1;0;n}` Meat
>         * `{1;0;0}` Product
>         * `{1;0;1}` Price
>         * `{1;0;2}` Color
>     * `{1;1;n}` Dairy
>         * `{1;1;0}` Product
>         * `{1;1;1}` Price
>         * `{1;1;2}` Color

In this 4-dimensionaL tree, every tree level has a *meaning* or, in other words, they represent distinct characteristic of the data it contains:

* The first level divides the data in Plant or Animal based products.
* The second level divides each of those main categories into their own unique subcategories
* The third level represents the different types of values we have fore each subcategory:
    * Product name
    * Product price
    * Product color

## Advanced Data Trees

## Advanced selection

## Structure relationships

## Advanced tree editing

# Good practices

## DRY

## Grouping

## Naming conventions

## Keeping things straight

# Teamwork

## Structuring a project

## Design input-output

## Putting it all together

## Making BIG changes

# Making it better

## Dynamic relaxation

## Galapagos

# BIM Interoperability

## Archicad Live Connection

## Rhino Inside (Advanced)
