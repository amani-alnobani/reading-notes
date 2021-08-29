# Readings: Introduction to React and Components

# Component-Based Architecture

### Component-based architecture focuses on the decomposition of the design into individual functional or logical components that represent well-defined communication interfaces containing methods, events, and properties. It provides a higher level of abstraction and divides the problem into sub-problems, each associated with component partitions.

### The primary objective of component-based architecture is to ensure component reusability. A component encapsulates functionality and behaviors of a software element into a reusable and self-deployable binary unit. There are many standard component frameworks such as COM/DCOM, JavaBean, EJB, CORBA, .NET, web services, and grid services. These technologies are widely used in local desktop GUI application design such as graphic JavaBean components, MS ActiveX components, and COM components which can be reused by simply drag and drop operation.

## What is a Component?
### A component is a modular, portable, replaceable, and reusable set of well-defined functionality that encapsulates its implementation and exporting it as a higher-level interface.

## Views of a Component
1. Object-oriented view
2. Conventional view
3. Process-related view
## What is “Props” and how to use it in React?
### React has a different approach to data flow & manipulation than other frameworks, and that’s why it can be difficult at the beginning to understand some concepts like props, state and so on.
### I believe it’s better to keep explaining them in separated posts and in this article, we’re going to focus on React’s Props feature and how to use it.

## What is Props?
#### React is a component-based library which divides the UI into little reusable pieces. In some cases, those components need to communicate (send data to each other) and the way to pass data between components is by using props.
### “Props” is a special keyword in React, which stands for properties and is being used for passing data from one component to another.
## Using Props in React
1. Firstly, define an attribute and its value(data)
2. Then pass it to child component(s) by using Props
3. Finally, render the Props Data

## Tutorial: Intro to React
### What Are We Building?
#### In this tutorial, we’ll show how to build an interactive tic-tac-toe game with React. You can see what we’ll be building here: Final Result. If the code doesn’t make sense to you, or if you are unfamiliar with the code’s syntax, don’t worry! The goal of this tutorial is to help you understand React and its syntax. We recommend that you check out the tic-tac-toe game before continuing with the tutorial. One of the features that you’ll notice is that there is a numbered list to the right of the game’s board. This list gives you a history of all of the moves that have occurred in the game, and it is updated as the game progresses. You can close the tic-tac-toe game once you’re familiar with it. We’ll be starting from a simpler template in this tutorial. Our next step is to set you up so that you can start building the game.

