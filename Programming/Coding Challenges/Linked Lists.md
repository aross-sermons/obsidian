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
1. Iterate through the linked list, adding the data of each element to an array.
2. Traverse the array backwards.
**Method #2** - Temporary Last Node
	This solution can be found in my library as singly_linked_list.py.
1. Use two temporary nodes. One starts at the head and the other starts at the tail.
2. After the first call, the temporary tail will become the next to last node.
3. For each call, move the temporary head node to the next node until its' next node is the next to last node.
4. Repeat recursively until the head is the last node.
**Method #3** - Reverse the List
1. Use a solution to challenge #2 to reverse the list.
2. Iterate forward.
### Challenge #2 - Reverse a Singly Linked List
**Method #1** - New List
1. Make a new list, starting with the tail and removing the tail from the original list.
2. Call recursively, passing the new list as a parameter and adding the old list's tail each time.
3. Return the new list.
**Method #2** - 
1. 
