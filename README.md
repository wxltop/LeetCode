记录力扣刷题进度。难度中，一颗:star2:表示`容易`，两颗:star2::star2:表示`中等`，三颗星:star2::star2::star2:表示`困难`。FM表示`Fully Mastered`表示是否完全掌握。
|线性表|二叉树|动态规划|贪心|回溯|占位符|占位符|占位符|占位符|
| :------------------------: | :------------------------------: | :--------------------: | :--------------------: | :----------------------------------: | :----------------------: | :----------------------: | :--------------------------: | :--------------------------: |
| [:sunflower:](#sunflower-线性表) | [:four_leaf_clover:](#four_leaf_clover-二叉树) | [:deciduous_tree:](#deciduous_tree-动态规划) | [:evergreen_tree:](#evergreen_tree-贪心) | [:cactus:](#cactus-回溯) | [:cherry_blossom:](#cherry_blossom-占位符) | [:maple_leaf:](#maple_leaf-占位符) |   [:palm_tree:](#palm_tree-占位符)   |   [:seedling:](#seedling-占位符)|
# :sunflower: 线性表
|**Problem**|**Difficulty**|**Tags***|**Method**|**Time/Space**|**FM**|**Note**|
| --------- | :----------: |---------| -------- | :----------: | :--: | ------ |
|[21.合并两个有序链表](https://leetcode.cn/problems/merge-two-sorted-lists/)|:star2:|`链表`|[1.双指针](https://leetcode.cn/submissions/detail/392819406/)<br />[简化后的代码](https://leetcode.cn/submissions/detail/392830186/)<br />[2.递归](https://leetcode.cn/submissions/detail/392837384/)|O(n)/O(1)<br />O(n)/O(1)<br />O(n+m)/O(n+m)|:white_check_mark:|注意哨兵节点的灵活使用，可以简化代码。递归思路：每一步合并操作都是将俩子链表较小的一个头结点合并过来，然后处理后续的节点，即head1.val+merge(head1.next, head2) 或者 head2.val+merge(head1, head2.next)|
|[86.单链表的分解](https://leetcode.cn/problems/partition-list/)|:star2::star2:|`链表`|[1.双指针](https://leetcode.cn/submissions/detail/393068538/)<br />[2.大小链表](https://leetcode.cn/submissions/detail/393075051/)|O(n)/O(1)<br />O(n)/O(1)<br />O(n+m)/O(n+m)||两种方法效率差不多，只不过处理逻辑有差别，双指针逻辑更复杂，双指针用指针从输入链表中取出较小节点插入所维护的链表中；大小链表维护两个链表，分别存储小值的节点和大值的节点，逻辑更容易理解|
|[23.合并k个升序链表](https://leetcode.cn/problems/merge-k-sorted-lists/)|:star2::star2::star2:|`链表`|[1.多指针](https://leetcode.cn/submissions/detail/393109365/)<br />|O(n)/O(1)<br />||多指针维护k个指针分别指向k个链表，循环每次从k个链表中获取当前层的最小值然后插入结果链表，当所有指针为空时退出循环。|






# :four_leaf_clover: 二叉树
# :deciduous_tree: 动态规划
# :evergreen_tree: 贪心
# :cactus: 回溯
