
红黑树
====================

学习红黑树之前，我们先简单了解一下二叉查找树（BST）

二叉查找树
--------------------
二叉查找树有一下几个特性：  
1.左子树的节点值均小于或等于其父节点值；  
2.右子树的节点值均大于或等于其福节点值；  
3.左右子树也一定是二叉排序树；

下图所示为一棵典型的二叉排序树  

                         9  
                       /    \ 
                      /      \
                     /        \
                    5          13
                   / \        /  \
                 2     7     11   15
                / \   / \    / \  /\
               1   3  6  8  10 12


这种结构有什么好处呢？那就是通过对比节点的值，很快能检索要要查找的值。比如查找值为10的节点：9 - 13 - 11 - 10

这不是二分查找的思想吗？确实，查找所需的最大次数等同于二叉查找树的高度。当然在插入节点的时候，也是这种思想，一层一层的找到合适的位置插入。但是二叉查找树有个比较大的缺陷，而且这个缺陷会影响到他的性能。我们先来看下有一种情况的插入操作：

如果初始的二叉查找树只有三个节点，如下图:

      9  
     / \  
    8   13  

依次插入5个节点：7、6、5、4、3

                        9  
                       / \  
                      8   13 
                     /
                    7
                   /
                  6
                 /
                5
               /
              4
             /
            3 

看出来了吗？有没有觉得很别扭，如果根节点足够大，那是不是“左腿”会变的特别长，也就是说查找的性能大打折扣，几乎就是线性查找了。

那有没有好的办法解决这个问题呢？解决这种多次插入新节点而导致的不平衡？这个时候红黑树就登场了。

红黑树简介
--------------------

红黑树有一下几个特征

1.节点是黑色或者红色；  
2.根结点是黑色；  
3.每个叶子结点都是黑色的空节点（NULL）；  
4.每个红色节点的子节点都是黑色的；  
5.对于每个节点，从该节点到树尾端节点（NULL）的任何路径，黑色节点的数量都相同。

