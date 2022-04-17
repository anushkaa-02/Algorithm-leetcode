# Trim a Binary Search Tree 
### Problem link: [Click me](https://leetcode.com/problems/trim-a-binary-search-tree/)
---

- ## Question: 
>Given the `root` of a binary search tree and the lowest and highest boundaries as `low` and `high`, trim the tree so that all its elements lies in `[low, high]`. Trimming the tree should **not** change the relative structure of the elements that will remain in the tree (i.e., any node's descendant should remain a descendant). It can be proven that there is a **unique answer.**
Return the root of the trimmed binary search tree. Note that the root may change depending on the given bounds.
>> Example :


        1                      1
       / \         ➡️           \  
      0   2                       2
      
---

- ## Solution:
**Approach :**
- We will collapse any branches that fall outside our given range from low L to high H.
- If root R is null, we should stop the recursion and return R back up. Then, we have a branch, depending on whether or not the value of R is < L or > H.
- If the value is too low, we want to pull up the branch to the right and continue the recursion, and vice versa if the value is too high.
- Otherwise, we just want to continue the recursion down each branch.

---
**Code :**

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
    TreeNode* trimBST(TreeNode* R, int L, int H) {
        if (!R) return R;
        if (R->val < L) return trimBST(R->right,L,H);
        else if (R->val > H) return trimBST(R->left,L,H);
        R->left = trimBST(R->left,L,H) ;
        R->right = trimBST(R->right,L,H);
        return R;
    }
};
```
---

Reference : [Dev to](https://dev.to/)
