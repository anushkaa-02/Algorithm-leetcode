# Search in a Binary Search Tree
### Problem link: [Click me](https://leetcode.com/problems/search-in-a-binary-search-tree/)
---

- ## Question: 
> You are given the root of a binary search tree (BST) and an integer val.
Find the node in the BST that the node's value equals val and return the subtree rooted with that node. If such a node does not exist, return null.
>> Given the tree:

        4
       / \
      2   7
     / \
    1   3
    
> And the value to search: 2.
>> You should return this subtree:

      2     
     / \   
    1   3
    
---

- ## Solution:
**Approach :**
- **Step 1 :** Check if the root is NULL or not. If the tree is empty, return NULL.
- **Step 2 :** If the root node’s value is equal to the key, then return the root node.
- **Step 3 :** If the root node’s value is less than the key value, then find the key in the right subtree.
- **Step 4 :** If we hit the tree end and couldn’t find the key, then, in that case, we will return NULL.

---
**Code :**

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    TreeNode* searchBST(TreeNode* root, int val) {
        if(root==NULL)return NULL;                   // If the root is NULL i.e the tree is empty, return NULL.
        else if (root->val == val)return root;       // If the root node's value matches the key, return that node.
        else if (root->val < val) return searchBST(root->right,val); /* If the key is greater than root node's value, 
                                                                            then it must be in right subtree.*/
        else return searchBST(root->left,val); // If the key is less than root node's value, then it must be in left subtree.
    }
};
```

**Time Complexity :**
- Balanced BST: O(log N)
- Unbalanced BST: O(N)

---
Reference: [The Coding bot](https://thecodingbot.com/)

    
