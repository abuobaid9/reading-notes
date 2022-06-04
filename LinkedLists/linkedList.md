# Linked List

## What is the Big O ?

Big O(oh) notation is used to describe the efficiency of an algorithm or function.

## How to find Big O ?

we should consider 4 Key Areas for analysis:

1. Input Size
2. Units of Measurement
3. Orders of Growth
4. Best Case, Worst Case, and Average Case.

## How we  quantify the Running Time ?

1. Quantify the Running Time.
2. Quantify Memory Space.

## What is Orders of Growth ?

 We can describe overall efficiency by using the input size n and measuring the overall Units of Space and Time required for the given input size n. As the value of n grows, the Order of Growth represents the increase in Running Time or Memory Space.

 ![Orders of Growth](./img/OrdersOfGrowth.png)

## Worst Case, Best Case, Average Case :-

* Worst Case: The efficiency for the worst possible input of size (n).

* Best Case: The efficiency for the best possible input of size (n).

* Average Case: The efficiency for a “typical” or “random” input of size (n).

## What is a Linked List?

A Linked List is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.

## Types of Linked Lists :-

---

1. Singly: Singly refers to the number of references the node A has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.

2. Doubly: Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.

## Traversal

When traversing a linked list, you are not able to use a foreach or for loop. We depend on the Next value in each node to guide us where the next reference is pointing. The Next property is exceptionally important because it will lead us where the next node is and allow us to extract the data appropriately.

---

## Traversal Big O

* The Big O of time for Includes would be O(n). This is because, at its worse case, the node we are looking for will be the very last node in the linked list. n represents the number of nodes in the linked list.

* The Big O of space for Includes would be O(1). This is because there is no additional space being used than what is already given to us with the linked list input.

---

## Adding a Node

Adding O(1)

Order of operations is extremely important when it comes to working with a Linked List. What I mean by this is you must be careful that all references to each link/node is properly assigned.

---

## Print Out Nodes

Printing out all of the nodes in a Linked List is very similar to what we did in the Includes() method. This is because we are leveraging our Current node and a while loop to traverse through the existing linked list.

---

## Prerequisites

When constructing your code, a few things to keep in mind.

When making your Node class, consider requiring a value to be passed in to require that each node has a value.
