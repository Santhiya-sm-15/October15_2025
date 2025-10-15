# October15_2025
The problem that I solved today

Given the root of a BST and an integer k, the task is to find the kth smallest element in the BST. If there is no kth smallest element present then return -1.

Code:
class Solution {
    int res;
    public void traverse(Node root,List<Integer> l)
    {
        if(root==null)
            return;
        traverse(root.left,l);
        l.add(root.data);
        traverse(root.right,l);
    }
    public int kthSmallest(Node root, int k) {
        List<Integer> l=new ArrayList<>();
        traverse(root,l);
        return l.size()>=k?l.get(k-1):-1;
    }
}
