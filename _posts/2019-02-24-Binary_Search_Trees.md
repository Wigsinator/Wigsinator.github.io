---
title: Binary Search Trees
category: csc290
---
Binary search trees are an incredibly useful and important tool for any computer scientist to know, as they allow us to store data such that it can be quickly found.

### What they are:

A binary search tree consists of 3 or 4 elements. 

1. a search key
2. an associated value (this is the optional one)
3. a left subtree or leaf node
4. a right subtree or leaf node

In a binary search tree, each subtree must also be a binary search tree. A leaf node exists to mark the end of the tree, and they are not distinguishable from one another.

However, the most important part of a binary search tree is that the search key of the root node is always greater than that of the left subtree, and always less than that of the right subtree.

### Why they're useful

The single biggest reason to use a binary search tree is their speed. For an average binary search tree, adding a node, finding a node, and deleting a node takes O(log n) time, with a worst case scenario of O(n) (expanded on in the next section), where n is the size of the tree. This is because the value being searched for, added, or deleted only needs to be compared to the nodes it is passing through, which if the tree is well constructed, should cut the tree in half for each level into the tree you go.

What's more, if you print out the tree, by recursively printing the left tree, the search key, and then the right tree, you get a perfectly sorted list of all the search keys.

### Some pitfalls to look out for

Obviously, a binary search tree can easily grow out of control if the root node and the order that other nodes are added is organized poorly.  
For example, say you have a tree with the search keys being the numbers 1 through 10. If you make 1 your root node, and add each other node in ascending order, you're going to end up with an unbalanced tree, with each node having a right subtree and a left leaf. This means that if you're trying to add a tree with a search key of 11, you're going to have to go through the entire tree, making it O(n).

### In conclusion

Binary search trees are, when well used, an incredibly powerful search database, and is definitely getting used to, and even if the pitfalls may seem intimidating, they're very worth your time to figure out.