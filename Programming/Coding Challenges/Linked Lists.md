---
title: Linked Lists
parent:
  - "[[Coding Challenge]]"
aliases: 
tags:
  - incomplete
  - wip
---
### Linked Lists
A list of individual nodes in which each node contains data and a pointer to the next node.
### Challenge #1 - Traverse a Singly Linked List in Reverse
**Method #1** - Copy as Array
	Iterate through the linked list, adding the data of each element to an array. Traverse the array backwards.
**Method #2** - Temporary Last Node
	Use one temporary node to point to the last node and another to point to the current. On first pass, iterate and set last as
