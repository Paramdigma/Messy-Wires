---
title: Introduction
catalogGraph:
  - word: Winter Is Coming
---

# {{ $page.title }}

<CatalogGraph />

Visual programming software, such as Grasshopper, is amost always based on the concept of **_nodes_**, wich can be connected in a chain like manner to create complex interactions between them.

Consider the following grasshopper nodes:

![Inputless component]()
![Outputless component]()
![Component with input and output]()

Grasshopper components can have any number of inputs and outputs, including none.

@flowstart ant

st=>start: Start:><http://www.google.com[blank>]
e=>end:><http://www.google.com>
op1=>operation: My Operation
sub1=>subroutine: My Subroutine
cond=>condition: Yes
or No?:><http://www.google.com>
io=>inputoutput: catch something...
para=>parallel: parallel tasks

st->op1->cond
cond(yes)->io->e
cond(no)->para
para(path1, bottom)->sub1(right)->op1
para(path2, top)->op1

@flowend
