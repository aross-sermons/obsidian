---
title: Singly Linked List
parent:
  - "[[Python Library|Python Library]]"
aliases: 
tags:
  - data-structure
  - python-module
  - complete
---
### Singly Linked List
A type of linked list.
### Development
**Official Name:** singly_linked_list.py with class SinglyLinkedList
**Definition**
	A singly linked list is a list of individual nodes which each point to their next node, but not to their previous node.
	Ex: 3 -> 7 -> 6 -> 0 -> 4
**Implementation**
	Contains a class Node and some module functions for manipulating a singly linked list.
**History**
	The Python implementation of this data structure is complete as of 7/29/24.
	Implementation started on 7/28/24.
### Class Variables
**Variables**
- data - the data to be stored
- next - the next node
### Class Functions
**__init__**
	Initializes a node with a given data value and next node (next defaults to None).
**__str__**
	Returns a human-readable string representation of the node.
**__repr__**
	Returns an unambiguous string representation of the node.
**get_tail**
	Returns the last node of the linked list stemming from self.
	Uses a while loop to iterate until `current_node.next == None`.
**forward_traverse**
	Prints each node stemming from self in normal order.
**backward_traverse**
	Prints each node stemming from self in reverse order.
	Each call iterates to the node before the previously printed node.