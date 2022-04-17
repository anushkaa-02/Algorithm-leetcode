# Increasing Order Search Tree
### Problem link: [Click me](https://leetcode.com/problems/increasing-order-search-tree/)
---

- ## Question: 
>Given the `root` of a binary search tree, rearrange the tree in **in-order** so that the leftmost node in the tree is now the root of the tree, and 
 every node has no left child and only one right child.
 - Constraints :
   - The number of nodes in the given tree will be in the range `[1, 100]`.
   - `0 <= Node.val <= 1000`
   
  > Example :
 
     Input: [5,3,6,2,4,null,8,1,null,null,null,7,9]
     
           5                               
          / \                               
        3    6                               
       / \    \                         
      2   4    8                                
     /        / \                                
    1        7   9                                
     
     Output: [1,null,2,null,3,null,4,null,5,null,6,null,7,null,8,null,9]
     
             1
              \
               2
                \
                 3
                  \
                   4
                    \
                     5
                      \
                       6
                        \
                         7
                          \
                           8
                            \
                             9  
                             
---

- ## Solution:
**Code :**
