# Convert BST to Greater Tree
### Problem link: [Click me](https://leetcode.com/problems/convert-bst-to-greater-tree/)
---

- ## Question:
> Given the root of a Binary Search Tree (BST), convert it to a Greater Tree such that every key of the original BST is changed to the original key plus 
  the sum of all keys greater than the original key in BST.
>> Example :

                        4
                       
                   /        \
                   
                 1             6
                  
               /   \         /   \
                
             0       2     5        7
               
                       \              \
                       
                          3             8
                       
                                      
     Input: root = [4,1,6,0,2,5,7,null,null,null,3,null,null,null,8]
     Output: [30,36,21,36,35,26,15,null,null,null,33,null,null,null,8]
     
---

- ## Solution:
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
    TreeNode* convertBST(TreeNode* root) {
         int cur_sum = 0;
        convertBSTHelper(root, &cur_sum);
        return root;
    }

private:
    void convertBSTHelper(TreeNode* root, int *cur_sum) {
        if (!root) {
            return;
        }

        if (root->right) {
            convertBSTHelper(root->right, cur_sum);
        }
        root->val = (*cur_sum += root->val);
        if (root->left) {
            convertBSTHelper(root->left, cur_sum);
        }
    }
};
```

**Time Complexity : O(n)**

---

Reference : [Dev to](https://dev.to/)


