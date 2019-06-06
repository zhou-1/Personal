# Threaded Binary Tree     

对于n个节点的二叉树，在二叉链存储结构中有n+1个空链域，利用这些空链域存放在某种遍历次序下该节点的前驱节点和后继节点的指针，这些指针称为线索，加上线索的二叉树称为线索二叉树（Threaded BinaryTree）    
现将节点结构重新定义如下：
    
    _leftTag = 1时 _leftchild指向左孩子    
    _leftTag = 0时 _leftchild指向前驱；
    _data   
    _rightTag = 1时_rightchild指向右孩子；
    _rightTag = 0时_rightchild指向后继。

建立线索二叉树，实质上就是遍历一颗二叉树并修改空指针的过程。在遍历的过程中，访问节点的操作是检查当前的左、右指针是否为空，将它们改为指向前驱节点或后继节点的线索。为实现这一过程，设指针prev始终指向刚刚访问过的节点，即若cur指向当前节点，则prev指向cur的前驱，以便设线索     


1、中序线索化二叉树：若节点的_leftTag = 0，_leftchild指向前驱；否则，该节点的前驱是以该节点为根的左子树上按中序遍历的最后一个节点。若_rightTag = 0，_rightchild指向后继；否则，该节点的后继是以该节点为根的右子树上按中序遍历的第一个节点。       





https://blog.csdn.net/demi_hu/article/details/70183267    


