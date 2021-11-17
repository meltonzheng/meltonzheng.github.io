---
pinned: true
tags: [notes]
title: Notes on Programiz DSA
created: '2021-11-16T22:36:35.359Z'
modified: '2021-11-16T23:41:17.787Z'
---

<div class="ui embed" data-url="https://www.youtube.com/embed/5qap5aO4i9A"></div>

# I. DSA Intro
## A. Types of Structures
### 1. Linear
They're sequences of elements. Prob not good once the line gets long.
### Types
#### a. Arrays
Contiguous memory.
C++ `int foo [5];`
`int foo[5];` 
Python `x = []` It uses lists as arrays
#### b. Stacks
Last In, First Out (LIFO).
In C++, it's in the [standard library](https://www.cplusplus.com/reference/stack/stack/). It can call functions 
- empty,
- size,
- back, 
- push_back, and
- pop_back.

#### c. Queues
First In, First Out (FIFO).
C++, it's also in the [standard library](https://www.cplusplus.com/reference/stack/stack/). 
Available functions:
- empty
- size
- front
- back
- push_back
- pop_front
There is also something called [priority queue](https://www.cplusplus.com/reference/queue/priority_queue/). I read it once, still not sure what it is tbh. 

#### d. Linked Lists
Elements connected as nodes.
Not an actual structure in C++. *Can implement.*

### 2. Non-Linear
Elements just randomly connected

#### a. Graphs
Node is vertex and vertex connects by an edge.
Popular Structures that use Graphs
- Spanning Tree and Minimum Spanning Tree ?
- Strongly connected Components ?
- Adjacency Matrix ?
* Adjacency List ?

#### b. Trees
Only one edge between two vertices.
- Binary Tree
- Binary Search Tree
- AVL Tree
- B-tree
- B+ Tree
- Red-Black Tree

## B. Algorithms

### Info
Bunch of examples on how optimizing cost saves $$, drives scability, and more
Things that stood out:
- Dijkstra's algorithm
- KMP algorithm

## C. Asymptotic Notations

### 1. Big O Notation O(f(x))
Formal definition:
> O(g(n)) = { f(n): there exist positive constants c and n0 
> such that 0 ≤ f(n) ≤ cg(n) for all n ≥ n0 }

Worst Case Scenario for the algorithm. Widely used.

### 2. Omega Ω(f(x))
> Ω(g(n)) = { f(n): there exist positive constants c and n0 
>            such that 0 ≤ cg(n) ≤ f(n) for all n ≥ n0 }

Best Case Scenario
### 3. Theta Θ(f(x))
> Θ(g(n)) = { f(n): there exist positive constants c1, c2 and n0
>            such that 0 ≤ c1g(n) ≤ f(n) ≤ c2g(n) for all n ≥ n0 }

Average Case Scenario

## C. Master Theorem
### 





















