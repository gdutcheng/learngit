this is resposity read me file.
try to build relationship between origin/master
and local/master 

Data Structures and algorithms
lesson one: red-black tree
https://www.cs.auckland.ac.nz/software/AlgAnim/red_black.html
https://www.cs.auckland.ac.nz/software/AlgAnim/red_black_op.html

struct t_red_black_tree {
  enum color {red, black},
  void * item,
  t_red_black_tree * left, right, parent
  
  // t_red_black_tree * uncle, grandparent  e树平衡操作时需要节点的uncle和grandparent
}

tree properties:
1）节点颜色只有红黑两种
2) 叶子节点为NULL，黑色
3) 红色节点的子节点只能是黑色
4) 每个节点到叶子节点的路径包含相同数量的黑色节点

red-black tree不是完全平衡的二叉数，左右子树的高度有可能相差2层，但是为了满足属性4，左右子树包含黑色节点的层数一定相等。

可以得出以下两个结论：
1.新插入的节点颜色是红色。反正法：如果是黑色，会导致新插入节点所在子树与另一边的子树所包含的黑色节点层数多一层，从而破坏了red-black tree的属性。
2.root node must be black。反证法：从第1点结论，如果根节点是红色，新插入节点是红色，那么子节点的插入都需要做树调整。

