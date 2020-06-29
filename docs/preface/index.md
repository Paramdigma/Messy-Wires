---
title: Preface
---

# {{ $page.title }}

::: tip Hi there!!👋🏻
First of all, thanks for visiting our book and taking an interest in Visual Programming using Grasshopper. Before we get started with the technical _(and fun 🎉)_ stuff, allow us to go through a little introduction.
:::

During the last 10 years, visual programming tools have become mainstream in many industries, transforming the way we design in the process.
This new tools allow architects and designers to create unprecedented designs, introducing unique features that have become the trademark image of many successfull architects.

However, these added capabilities usually come at a price: these higher level programming environments are the result of bringing coding concepts into the design space and, as such, benefitting from them requires a broad understanding of the underlying logic these programs follow.

In this book, we will cover some of this concepts using Rhinoceros Grasshopper, a very popular visual programming software, that is widely used in many industries.

It's title, _Messy Wires_, makes allusion to one of the main problems when creating successfull visual programming scripts at a professional level: _code clarity_, wich we will explain in more detail in [INSERT_REFERENCE].

We will start by understanding Grasshopper _Data Trees_, explaining the logic behind how they work, and how to properlly use them to introduce complexity in our designs while at keeping the size of our scripts manageable.

We will also cover some visual programming good practices, such as grouping, naming conventions, structuring and ordering scripts and some concepts directly inherited from programing, such as DRY (Don't Repeat Yourself).

More...

- Scripting
- BIM Connection
- Teamwork

## About this book

This book was written by [Paramdigma](https://paramdigma.com), a computational geometry collective based in Barcelona. It is released under a combination of MIT and CreativeCommons license _(book contents are CC, all code and gh files shared under MIT)_

This is a collaborative effort that you, as a reader, are **more than welcome** to take part of. We welcome all contributions, no matter how small. We organize all work through it's own [GitHub Repo](https://github.com/paramdigma/messy-wires), so feel free to open an issue to correct anything, or create a Pull Request if you feel like we missed something!

## Who is this book for ❔

**_Messy Wires_** is a book that centers around the concept of creating understandable adn mantainable visual programming scripts using Grasshopper. It is intended as a general introduction to already established best-practices in the coding world; therefore, we will asume that you already know the basics of how Grasshopper works, you are familiar with most of Grasshopper's default components and are comfortable creating medium sized scripts.

### ...is it focused on any specific design field ❔

Our aim is to make this book as _Grasshopper generic_ as possible, meaning it will not be focused on a specific design or engineering background. That being said, all of the Paramdigma team are **architects** and **building engineers**, so you might see a little influence of that in some of our examples 😅.

### 🤔...ok, this is not me ❕

If you are getting started with Grasshopper, that is ok! We've all been there. There are already many good introduction books and courses out there, their authors have done an amazing job and we didn't think it was worth repeating the same information. Check below a list of usefull Grasshopper resources

:::::: details Grasshopper Beguinner Resources

- [Grasshopper Primer](https://www.modelab.is/grasshopper-primer) — Written by ModeLab, it's an amazing learning resource.
- [David Rutten's Beguinners Course](https://link) — From GH's creator himself
- [David Rutten's Advanced Course](https://link) — From GH's creator himself
- [ThinkParametric](http://thinkparametric.com) — This one is not free, but it's definitely worth it!

::: warning Contributions accepted
If you know of any other **useful resources** not listed here, give us a shout-out and we'll gladly add them!
:::

::::::

## How to use this book

This book contains multiple example files, that will be uploaded at the books own GitHub Repository.

Throughout the book, you will find links to the appropriate files for each section.

Since we will be using Grasshopper as our main tool, most of the files will be saved in `.ghx` format, which is 'friendlier' to 'git', the version control software we use (and love! ❤️).

## Technical requirements

Since this is book for [Grasshopper](https://grasshopper3d.com) users, having [Rhino 6](https://rhino3d.com) installed is the only requirement.

> We will make our best efforts to use only cross-platform compatible plug-ins (meaning, they will work in Mac and Windows). But there will be cases where we might recommend a plug-in that is Windows only.
> This is the case of `SnappingGecko` a very handy plugin for node alignment.
