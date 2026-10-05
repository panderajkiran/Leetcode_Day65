# Leetcode_Day65
# Day 65 — Validate Binary Search Tree

## Problem

Given the root of a binary tree, determine whether it is a valid Binary Search Tree (BST).

A valid BST follows these rules:

- Every value in the left subtree must be strictly smaller than the current node.
- Every value in the right subtree must be strictly greater than the current node.
- Both left and right subtrees must also follow the BST rules.

---

## Approach

I used **recursion with a valid range** for every node.

Instead of checking only the direct left and right children, I keep track of the minimum and maximum values that each node is allowed to have.

For every node:

- Its value must be greater than `min`.
- Its value must be smaller than `max`.
- For the left subtree, the maximum becomes the current node's value.
- For the right subtree, the minimum becomes the current node's value.

I used `Long.MIN_VALUE` and `Long.MAX_VALUE` initially so that the complete integer range can be handled safely.

### Example

For a node with value `10`:

- Left subtree → values must be between `min` and `10`
- Right subtree → values must be between `10` and `max`

This range is updated as we move deeper into the tree.

---

## Complexity

### Time Complexity
`O(n)`

Every node is visited once.

### Space Complexity
`O(h)`

Where `h` is the height of the tree because of the recursive call stack.

---

## What I Learned

Today I learned that validating a BST is not just about checking whether:

- left child < current node
- right child > current node

A node deep inside the tree must also satisfy the restrictions created by its ancestors.

Using a range makes this relationship much easier to understand and implement.

---

## Key Takeaway

Sometimes the easiest way to solve a tree problem is not to look at a node alone, but to remember the rules passed down to it from the nodes above.

**The bigger picture matters just as much as the current step.**
