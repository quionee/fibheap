# Fibonacci Heap

## Fibonacci Heap Overview

The data structured and its operations are described Cormen et al. (chapter 19) Fibonacci heap supports mergeable-heap operations, including make-heap, insert, minimum, extract-min, and union. The data structure also supports key-decrease and delete, although using these two operations requires users to create nodes for items themselves.

## Representation 

### Node
Each node has the following attributes:
- left, right: the node's adjacent siblings. The node and its siblings are doubly linked, so they form a circular loop. If x is an only child, it is its own left and right sibling.
- child: the representative child of the node. To access all the children of the node, first access the representative child, then access all the representative child's siblings through left and right attributes
- parent
- degree: the number of the node's children
- mark: (description by Cormen et al.) is either True or False, indicating whether the node has lost a child since the last time it was made the child of another node. Newly created nodes are unmarked. A node becomes unmarked whenever it is made the child of another node. 

### Fibonacci Heap
A heap has the following attributes:
- min: points to the node that contains the minimum key
- number of nodes currently in the heap
- number of roots in the tree. A Fibonacci heap can contain many trees of min-ordered heap. The roots of these trees are doubly linked and form a circular loop as in the case with siblings. The number of trees of a Fibonacci heap is always the number of roots.
- number of marked nodes in the heap

## Operations Overview

### make-heap

Runs in $\Theta(1)$ worst-case time. Initializes an empty heap.

### insert

Runs in $\Theta(1)$ worst-case time. Adds the node as a root of the heap.

### minimum

Runs in $\Theta(1)$ worst-case time. Returns the min attribute of the heap.

### extract-min

Runs in $O(lg\:n)$ amortized time. Removes and returns the minimum node. This procedure moves each of the minimum node's children to the root list, removes the minimum node itself from the root list, and consolidates the resulted tree to reduces the number of trees.

### union

Runs in $\Theta(1)$ worst-case time. Makes and returns a union of two heaps. This procedure simply concatenates the two root lists.

### decrease-key

Runs in $O(1)$ amortized time. Decreases node x's key to k. 

### delete

Runs in $O(lg\:n)$ amortized time. Remove x from the heap by first setting its key to minus infinity and extracting the heap's min.

# Example
![](https://latex.codecogs.com/gif.latex?%5CTheta%28n%29)
