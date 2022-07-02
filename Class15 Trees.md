# ***Read: Class 15 - Trees***

***

## **Common Terminology:**

- Node - A Tree node is a component which may contain its own values, and references to other nodes.
- Root - The root is the node at the beginning of the tree.
- K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
- Left - A reference to one child node, in a binary tree.
- Right - A reference to the other child node, in a binary tree.
- Edge - The edge in a tree is the link between a parent and child node.
- Leaf - A leaf is a node that does not have any children.
- Height - The height of a tree is the number of edges from the root to the furthest leaf.

Sample Tree:

![](./Class-15%20images/BinaryTree1.png)

***

## **Traversals:**

An important aspect of trees is how to traverse them. Traversing a tree allows us to search for a node, print out the contents of a tree, and much more! There are two categories of traversals when it comes to trees:

## - Depth First:

Depth first traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to carry out depth first traversal, and each method changes the order in which we search/print the root. Here are three methods for depth first traversal:

* Pre-order: root >> left >> right:

        ALGORITHM preOrder(root)
        // INPUT <-- root node
        // OUTPUT <-- pre-order output of tree node's values

        OUTPUT <-- root.value

        if root.left is not Null
            preOrder(root.left)

        if root.right is not NULL
            preOrder(root.right)

* In-order: left >> root >> right:

        ALGORITHM inOrder(root)
        // INPUT <-- root node
        // OUTPUT <-- in-order output of tree node's values

        if root.left is not NULL
            inOrder(root.left)

        OUTPUT <-- root.value

        if root.right is not NULL
            inOrder(root.right)

* Post-order: left >> right >> root:

        ALGORITHM postOrder(root)
        // INPUT <-- root node
        // OUTPUT <-- post-order output of tree node's values

        if root.left is not NULL
            postOrder(root.left)

        if root.right is not NULL
            postOrder(root.right)

        OUTPUT <-- root.value

![](./Class-15%20images/tree-example.png)

![](./Class-15%20images/DepthTraversal11.png)

## - Breadth First

Breadth first traversal iterates through the tree by going through each level of the tree node-by-node. So, given our starting tree one more time:

![](./Class-15%20images/tree-example.png)

Our output using breadth first traversal is now:

Output: A, B, C, D, E, F

![](./Class-15%20images/BreadthTraversal8.png)

Here is the pseudocode, utilizing a built-in queue to implement a breadth first traversal.

    ALGORITHM breadthFirst(root)
    // INPUT  <-- root node
    // OUTPUT <-- front node of queue to console

    Queue breadth <-- new Queue()
    breadth.enqueue(root)

    while ! breadth.is_empty()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    if front.left is not NULL
        breadth.enqueue(front.left)

    if front.right is not NULL
        breadth.enqueue(front.right)

***

## **K-ary Trees:**

If Nodes are able have more than 2 child nodes, we call the tree that contains them a K-ary Tree. In this type of tree we use K to refer to the maximum number of children that each Node is able to have.

## - Breadth First Traversal:

Traversing a K-ary tree requires a similar approach to the breadth first traversal. We are still pushing nodes into a queue, but we are now moving down a list of children of length k, instead of checking for the presence of a left and a right child.

![](./Class-15%20images/KaryTree1.png)

If we traversed this tree Breadth First we should see the output:

Output: A, B, C, D, E, F, G, H

- We will still start at the root Node, and we will add it to our queue:

- Much like before, as long as we have a node in our queue we can dequeue:

![](./Class-15%20images/BreadthKary14.png)

This process is very similar to our binary tree traversal, but now we check a list of children instead of a left and right child properties. It should look something like this:

    ALGORITHM breadthFirst(root)
    // INPUT  <-- root node
    // OUTPUT <-- front node of queue to console

    Queue breadth <-- new Queue()
    breadth.enqueue(root)

    while ! breadth.is_empty()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    for child in front.children
        breadth.enqueue(child)

***
***

## **Binary Search Trees:**

A Binary Search Tree (BST) is a type of tree that does have some structure attached to it. In a BST, nodes are organized in a manner where all values that are smaller than the root are placed to the left, and all values that are larger than the root are placed to the right.

Here is how we would change our Binary Tree example into a Binary Search Tree:

![](./Class-15%20images//BST1.png)

earching a BST can be done quickly, because all you do is compare the node you are searching for against the root of the tree or sub-tree. If the value is smaller, you only traverse the left side. If the value is larger, you only traverse the right side.

![](./Class-15%20images//BST2.png)

The best way to approach a BST search is with a while loop. We cycle through the while loop until we hit a leaf, or until we reach a match with what we’re searching for.

***

[README](README.md)
