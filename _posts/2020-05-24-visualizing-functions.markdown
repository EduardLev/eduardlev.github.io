---
layout: post
title:  "Visualizing Types and Functions"
subtitle: "A quick introduction to category theory as it applies to Swift"
date: 2020-05-24 02:27:15 -0400
categories: jekyll update
tags: functional_programming swift category_theory
---
Visuals can help us understand and deal with the complexity of our code. To start creating
these visuals, we can first read the code, understand what data is available, and
how that data is manipulated. For example, when we are writing a screen for an iOS app,
Apple recommends the [MVC][MVC] pattern, which chunks screen code into three parts:
Model, View and Controller. This allows us to manage our program's complexity.
There is a lot of documentation on the role of each object in this architecture, but a diagram speaks a thousand words:

<div style = "text-align:center"><img src="/assets/model-view-controller.png" width="80%"></div><br>

In the above, we can see that a View does not communicate directly with the Model, since
there are no arrows connecting the two. A Controller has two way communication
with both Model and View. Keeping this image as a mental model will make it
easier to write code that follows this architecture.

# More Granular Visualizations

But why stop at architecture? We can extend the idea of visual mental models to even
smaller components - Types and Functions. A type can be thought of as some organized data, and it plays
a similar role as the View, Controller and Model objects in the above diagram. A function is a
transformation of types, and plays the role of the arrows between diagram objects.

To visualize types and functions, we can treat types as objects (dots) in a graph,
and functions as arrows between objects. Here's a `Swift` function named `f` that transforms an `Int` type into a `String`,
along with its corresponding diagram:

{% highlight swift %}
func f(_ input: Int) -> String {
  return "\(input)"
}
{% endhighlight %}

<div style = "text-align:center"><img src="/assets/int_to_string.jpeg" width="40%"></div><br>

The diagram cuts through the syntax and shows us the underlying structure of this function.
Imagine we had another function named `g` that returned the first character of a `String` input:

{% highlight swift %}
func g(_ input: String) -> Character {
  return input[0]
}
{% endhighlight %}

In the course of writing our code, we might find ourselves with some `Int` data that we want to
convert to `Character`. You can read the functions `f` and `g` and notice that the output of one
matches the input to the other. Therefore, to convert an `Int` to a `Character`, first pass it to `f`, and then
pass the output to `g`. Here is the diagrammatic translation of that:

<div style = "text-align:center"><img src="/assets/int_to_string_to_character.jpeg" width="40%"></div><br>

The diagram makes it clear that by starting with `Int` and following the arrows, you will arrive
at the `Character` type. It cuts through the language syntax and shows you the "structure"
of the code you are working with. This can make it easier to see new connections, refactor complex code,
and intuit about transformations.

In this simple example, we also could have gone directly from `Int` to `Character` by using or
defining a third function. What the diagram shows us is that this is not necessary, since
we already have all the transformations we need to manipulate the data in the way we want.

# Generalizing Graphs: Category Theory

The function diagram is an example of a **labeled directed graph**, where the nodes
of the graph correspond to programming types, and the directed edges (arrows) correspond to
functions (also called morphisms). The branch of mathematics that analyzes this visual structure
is called Category Theory. It's more than just drawings of dots and arrows though - there are some
rules that the graphs have to adhere to, and it's these rules that direct us in how to draw more complex diagrams.
Visualizing these complex diagrams can give us a clearer understanding of the lower level architecture
of our code in much the same way that the MVC diagram can lead us towards a cleaner higher level architecture.

The following shows more types, along with the functions we have previously defined, in a larger container
called a **Category**, which holds our nodes and arrows:

<div style = "text-align:center"><img src="/assets/simple_category.jpeg" width="60%"></div><br>

There is much more to say about the rules of drawing this graph, and how those rules apply
specifically to programming types. For instance, we can only apply most of the analyses of category theory
to functions that do not have any side effects -  these functions are typically called **pure**.

Drawing this graph can give us visual insights into the relationships between the
types and functions in our programs. In the above example, we were able to visualize
the relationship between functions `f` and `g`, and this was with nothing more than dots and arrows.
When asking if a certain transformation can be performed, it is sufficient only to draw the
graph and ask the same questions visually.

For more information on how to build these graphs, see Bartosz Milewski's
[wonderful blog][bartosz], which goes into detail on the mathematics of category theory and its connection to programming.

[MVC]: https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/MVC.html
[bartosz]: https://bartoszmilewski.com/2014/10/28/category-theory-for-programmers-the-preface/
