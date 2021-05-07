---
layout: post
title:  "Programming With Categories"
subtitle: "Notes on Lecture 0 of Programming with Categories"
date: 2021-05-07 01:54:15 -0400
tags: functional_programming swift category_theory
---
## Lecture 0 Notes
_The following are my notes and thoughts from the following lecture on category theory: [Programming With Categories - Lecture 0](https://youtu.be/NUBEB9QlNCM)._

Category theory is an abstract branch of mathematics while programming is a _practical_ tool. How do the two relate to each other? How can one help us with the other, and vice versa? A quote from the lecture summarizes the connection perfectly:

> Nothing’s perfectly math … There is a pure side for thinking, and applied side for doing.

The definitions and the rules of category theory are powerful tools for thinking about structures and connections between abstract entities. If applied in a certain way, you can simplify your practical programs. However, it can also work the other way round. Programming can be used to stress test your intuitions and conclusions about the mathematics. In short, use the concepts of category theory to write and decompose your programs. But also, use your programs to test and strengthen your understanding of category theory!

An example of structural patterns that might be familiar to programmers are the “Gang Of Four” design patterns, which takes common programming formulations and gives them names (i.e. Builder, Singleton, etc.). In our day to day task of engineering problem solving, we will run into situations where we have to simplify our programs to make them understandable to us (humans). The techniques with which we do so are sometimes common enough to be abstracted into general patterns. Category theory provides us with a rigorous mathematical framework for such abstractions.

This sequence of lectures will focus on providing an overview of the mathematics of category theory as well as its connections to programming (specifically types and functions). We will find that we can relate many useful programming concepts to the abstract mathematical ideas found in category theory:

Universal Constructors -> Abstract Data Types
Algebras & Coalgebras -> Recursive Data Types
Monads -> Composition & Side Effects

As I gain more experience as a programmer, I do find the same kinds of problems arising again and again. What kinds of functions and data types do I create, and how do I combine them together in order to achieve an end product that satisfies the required constraints and is also easy to understand, modify & test?
