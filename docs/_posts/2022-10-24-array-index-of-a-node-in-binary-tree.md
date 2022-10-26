---
layout: post
title: Array index of a node in a binary tree
katex: true
---
If we encode a complete binary tree to an array (e.g. priority queue), 
a parent node and two child nodes have a certain relationship in their indices. 
With that, we can easily navigate binary tree up and down. 
It seems just obvious. 
However, I cannot come up with a simple proof.
Moreover, when I googled, articles in page 1 do not include the proof.
Maybe it is too simple to explain the proof.
But I want the proof!

#### Prove ####
When a complete or full binary tree $$T$$ is represented by an array and
a node `n` has the index $$i$$, 
then the index of the left and the right child node is $$2i + 1$$ and $$2i + 2$$, respectively.

In other worlds, if `I(n) = i`, then `I(n.left) = 2i + 1`, `I(n.right) = 2i + 2`)


#### Proof ####
Let us assume that the node `n` is located at the $$k$$-th level from the top and 
the $$j$$-th offset from the left at the $$k$$-th level.

The number of the nodes until $$(k-1)$$-th level: 

$$S = 2^0 + 2^1 + \dots + 2^{k-1} = 2^k - 1$$ 

That is, $$i = 2^k + j - 2$$.

$$j - 1$$ nodes before the node $$n$$ will have $$2(j - 1)$$ children at $$(k+1)$$-th level.

Then `I(n.left)` 

$$=$$ # of nodes before `n.left`

$$=$$ # of nodes until $$k$$-th level $$+$$
      # of nodes at $$(k+1)$$-th level before `n.left`

$$= 2^{k+1} - 1 + 2(j - 1)$$ <p> &#8205;</p>

$$= 2^{k+1} + 2j - 3$$ <p> &#8205;</p>

$$= 2i + 1$$ <p> &#8205;</p>


Similarly, `I(n.parent) = (i - 1)//2`, where `//` is the floor division operator in Python.




