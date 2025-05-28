### Overview
---
The centroid of a tree is different from the center of a tree. A **centroid** is the node that when removed will yield subtrees where all subtrees have at most $n/2$ nodes. The center of the tree is the node that maximizes the height of a tree.

A tree will always have a centroid
### How to find centroid
---
The centroid of a tree can be found be picking an arbitrary node and recursively find the centroid on the subtree with more than $n/2$ nodes. The new candidate centroid will be recursively called on the neighbor of the original centroid.
### Amazing Resources
---
[A Visual Introduction to Centroid Decomposition](https://medium.com/carpanese/an-illustrated-introduction-to-centroid-decomposition-8c1989d53308)


