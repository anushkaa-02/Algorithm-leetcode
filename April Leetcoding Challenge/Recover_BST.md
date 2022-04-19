# Recover Binary Search Tree
### Problem link: [Click me](https://leetcode.com/problems/recover-binary-search-tree/)
---
- ## Question:
> You are given the `root` of a binary search tree (BST), where the values of **exactly** two nodes of the tree were swapped by mistake. Recover the tree without changing its structure.
>> Example :
    
            1               3
           /               /
          3      ➡️      1   
           \               \
            2               2
            
            
    Input: root = [1,3,null,null,2]
    Output: [3,1,null,null,2]
    Explanation: 3 cannot be a left child of 1 because 3 > 1. Swapping 1 and 3 makes the BST valid.
    
---

- ## Solution:
**Code :(Approach: Recursive)**

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    void recoverTree(TreeNode* root) {
        inorder(root);
    swap(x, y);
  }

 private:
  TreeNode* pred = nullptr;
  TreeNode* x = nullptr;  // 1st wrong node
  TreeNode* y = nullptr;  // 2nd wrond node

  void inorder(TreeNode* root) {
    if (!root)
      return;

    inorder(root->left);

    if (pred && root->val < pred->val) {
      y = root;
      if (!x)
        x = pred;
      else
        return;
    }
    pred = root;

    inorder(root->right);
  }

  void swap(TreeNode* x, TreeNode* y) {
    const int temp = x->val;
    x->val = y->val;
    y->val = temp;
        
    }
};
```
**Time Complexity : O(n)**

---

Reference : [Dev to](https://dev.to/)
