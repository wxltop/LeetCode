记录力扣刷题进度。难度中，一颗:star2:表示`容易`，两颗:star2::star2:表示`中等`，三颗星:star2::star2::star2:表示`困难`。FM表示`Fully Mastered`表示是否完全掌握。
|线性表|二叉树|动态规划|贪心|回溯|占位符|占位符|占位符|占位符|
| :------------------------: | :------------------------------: | :--------------------: | :--------------------: | :----------------------------------: | :----------------------: | :----------------------: | :--------------------------: | :--------------------------: |
| [:sunflower:](#sunflower-线性表) | [:four_leaf_clover:](#four_leaf_clover-二叉树) | [:deciduous_tree:](#deciduous_tree-动态规划) | [:evergreen_tree:](#evergreen_tree-贪心) | [:cactus:](#cactus-回溯) | [:cherry_blossom:](#cherry_blossom-占位符) | [:maple_leaf:](#maple_leaf-占位符) |   [:palm_tree:](#palm_tree-占位符)   |   [:seedling:](#seedling-占位符)|
# :sunflower: 线性表
|**Problem**|**Difficulty**|**Tags***|**Methods****|**Time**|**Space**|**FM**|**Note**|
| --------- | :----------: |---------| ---------- | :-----: | :-----: | :--: | ------ |
|[21.合并两个有序链表](https://leetcode.cn/problems/merge-two-sorted-lists/)|:star2:|`链表`|[1.双指针](https://leetcode.cn/submissions/detail/392819406/)<br />[2.简化后的代码](https://leetcode.cn/submissions/detail/392830186/)<br />[3.递归](https://leetcode.cn/submissions/detail/392837384/)|$O(n)$<br />$O(n)$<br />$O(n+m)$|$O(1)$<br />$O(1)$<br />$O(n+m)$|:white_check_mark:|注意哨兵节点的灵活使用，可以简化代码。递归思路：每一步合并操作都是将俩子链表较小的一个头结点合并过来，然后处理后续的节点，即head1.val+merge(head1.next, head2) 或者 head2.val+merge(head1, head2.next)|
|[86.单链表的分解](https://leetcode.cn/problems/partition-list/)|:star2::star2:|`链表`|[1.双指针](https://leetcode.cn/submissions/detail/393068538/)<br />[2.大小链表](https://leetcode.cn/submissions/detail/393075051/)|$O(n)$<br />$O(n)$<br />$O(n+m)$|$O(1)$<br />$O(1)$<br />$O(n+m)$||两种方法效率差不多，只不过处理逻辑有差别，双指针逻辑更复杂，双指针用指针从输入链表中取出较小节点插入所维护的链表中；大小链表维护两个链表，分别存储小值的节点和大值的节点，逻辑更容易理解|
|[23.合并k个升序链表](https://leetcode.cn/problems/merge-k-sorted-lists/)|:star2::star2::star2:|`链表`|[1.多指针](https://leetcode.cn/submissions/detail/393109365/)<br />[2.顺序合并](https://leetcode.cn/submissions/detail/393285831/)<br />[3.分治合并](https://leetcode.cn/submissions/detail/393297388/)|$O(k^2n+k^2/2)$<br />$O(k^2n)$<br/>$O(knlogk)$|$O(1)$<br />$O(1)$<br />$O(logk)$||多指针维护k个指针分别指向k个链表，循环每次从k个链表中获取当前层的最小值然后插入结果链表，当所有指针为空时退出循环。顺序合并先解决两个顺序链表的合并问题，然后按顺序两两合并。分治合并使用分治算法完成。官方解读还有一种[优先队列(二叉堆)](https://leetcode.cn/problems/merge-k-sorted-lists/solution/he-bing-kge-pai-xu-lian-biao-by-leetcode-solutio-2/)的方法，该方法和多指针法很相似，只不过其用一个堆维护k个链表头最小值，而多指针直接用传进来的plist，每次都要选最小值，链表为空时删除。|
|[19.删除链表的倒数第n个节点](https://leetcode.cn/problems/remove-nth-node-from-end-of-list/)|:star2::star2:|`链表`|[1.O(L)空间复杂度](https://leetcode.cn/submissions/detail/393109365/)<br />[2.计算链表的长度](https://leetcode.cn/submissions/detail/393691518/)<br />[3.双指针](https://leetcode.cn/submissions/detail/393764158/)|$O(L)$<br/>$O(2L-n+1)$<br/>$O(L)$ | $O(L)$<br />$O(1)$<br/>$O(1)$||双指针比较巧妙，两个指针间隔n-1|
 |[876.链表的中间节点](https://leetcode.cn/problems/middle-of-the-linked-list/)|:star2:|`链表`<br/>`快慢指针`|[1.双指针](https://leetcode.cn/submissions/detail/393788629/)<br/>[2.快慢指针](https://leetcode.cn/submissions/detail/393795468/)|$O(n)$<br/>$O(n/2)$ |$O(1)$<br/>$O(1)$ ||双指针的思路是用一个指针一直往后遍历，另一个指针始终指向中间节点；快慢指针的思路是快指针每次跑两个节点，慢指针每次跑一个节点，所以慢指针始终处于中间位置|
|[141.环形链表](https://leetcode.cn/problems/linked-list-cycle/)|:star2:|`链表`<br/>`快慢指针`|[1.快慢指针](https://leetcode.cn/submissions/detail/394187671/)<br/>[2.哈希表](https://leetcode.cn/submissions/detail/394218224/)|$O(n)$<br/>$O(n)$ |$O(1)$<br/>$O(n)$ ||**可证明：慢指针进入环后第一圈内必定与快指针相遇；快指针速度为慢指针的n倍，二者相遇时间不随n增大而减少**|
|[142.环形链表II](https://leetcode.cn/problems/linked-list-cycle-ii/)|:star2::star2:|`链表`<br/>`快慢指针`|[1.快慢指针](https://leetcode.cn/submissions/detail/394251424/)<br/>[2.哈希表](https://leetcode.cn/submissions/detail/394219009/)|$O(n)$<br/>$O(n)$ |$O(1)$<br/>$O(n)$ ||快慢指针思想是利用快指针和慢指针可以计算出慢指针距离环的入口的长度，设为c，设链表距离环入口长度为a，可以得到a=(n-1)L+c，也就是说重新定义一个指针从链表头开始走，慢指针继续走下去，二者一定会相遇且第一次相遇点在环的入口处。|
|[160.相交链表](https://leetcode.cn/problems/intersection-of-two-linked-lists/)|:star2:|`链表`|[1.双指针](https://leetcode.cn/submissions/detail/394490567/)<br/>[2.哈希表](https://leetcode.cn/submissions/detail/394282945/)|$O(n-m+a)$<br/>$O(n+m)$ | $O(n)$<br/>$O(1)$||双指针方法较巧妙，先从各自头部开始，短链表结束后从长链表出发，长链表走完后从短链表出发，此时二者剩余步长相等，接下来每一步都判断一下是否相等即可。简化代码可以考虑到，结束程序的时候是二者相等，不论是None还是相交|
|[206.反转链表](https://leetcode.cn/problems/reverse-linked-list/)|:star2:|`链表`|[1.栈](https://leetcode.cn/submissions/detail/394901007/)<br/>[2.多指针](https://leetcode.cn/submissions/detail/394951064/)<br/>[3.双指针](https://leetcode.cn/submissions/detail/394982734/)<br/>[4.递归](https://leetcode.cn/submissions/detail/395327986/)<br/>[5.特殊双指针](https://leetcode.cn/submissions/detail/395529053/)|$O(2n)$<br/>$O(n)$<br/>$O(n)$<br/>$O(n)$<br/>$O(n)$ | $O(n)$<br/>$O(1)$<br/>$O(1)$<br/>$O(n)$<br/>$O(1)$||2.多指针和3.双指针思路差不多，但是多指针的实现不够简洁|
|[92.反转链表II](https://leetcode.cn/problems/reverse-linked-list-ii/)|:star2::star2:|`链表`|[1.特殊双指针](https://leetcode.cn/submissions/detail/395610365/)<br/>[2.一次遍历](https://leetcode.cn/submissions/detail/395617734/)|$O(n)$<br/>$O(n)$ | $O(1)$<br/>$O(1)$||特殊双指针是基于206.反转链表完成的，先找到需要反转的子链表头结点和尾节点，返回翻转后的链表，再接上。这样方法的缺点是，如果left和right区间很大，则耗时。方法2就是解决这个问题，一次遍历。起初我自己的想法是，到了left开始翻转，记录left前一个节点，反转到right结束，记录right下一个节点，然后拼接。但是官方给的思路是，在翻转区域内，将后一个节点插到翻转区域的头部。这里代码实现的是官方的思路。官方实现的一次遍历在返回结果的时候不用分类讨论，也就是常遇到的特殊情况问题。|
|[24.两两交换链表中的节点](https://leetcode.cn/problems/swap-nodes-in-pairs/)|:star2::star2:|`链表`|[1.多指针](https://leetcode.cn/submissions/detail/396174197/)<br/>[2.递归](https://leetcode.cn/submissions/detail/396508688/)|$O(n)$<br/>$O(n)$ | $O(1)$<br/>$O(n)$|||
|[25.K个一组翻转链表](https://leetcode.cn/problems/reverse-nodes-in-k-group/)|:star2::star2::star2:|`链表`|[1.多指针](https://leetcode.cn/submissions/detail/396587930/)<br/>|$O(n)$ | $O(1)$||此题要先知道接下来是否有k个节点才决定是否翻转。如果不提前计数，最终还需要还原不足的k个节点。一种方式是翻转前统计整个链表节点数，决定需要翻转的子链表数目；一种方式是每次翻转子链表前统计是否够k个。|
|[328.奇偶链表](https://leetcode.cn/problems/odd-even-linked-list/)|:star2::star2:|`链表`|[1.多指针](https://leetcode.cn/submissions/detail/396590304/)<br/>|$O(n)$ | $O(1)$||用一个计数器判断当前是奇数还是偶数，奇数就将当前节点连接到奇数链表上，偶数就将当前节点连接到偶数链表上。|
|[203.移除链表元素](https://leetcode.cn/problems/remove-linked-list-elements/)|:star2:|`链表`|[1.多指针](https://leetcode.cn/submissions/detail/396591269/)<br/>|$O(n)$ | $O(1)$|||
|[82.删除排序链表中的重复元素ii](https://leetcode.cn/problems/remove-duplicates-from-sorted-list-ii/)|:star2::star2:|`链表`|[1.多指针](https://leetcode.cn/submissions/detail/396648104/)<br/>|$O(n)$ | $O(1)$|||
|[148.排序链表](https://leetcode.cn/problems/sort-list/)|:star2::star2:|`链表`|[1.多指针](https://leetcode.cn/submissions/detail/396651065/)<br/>|$O(n^2)$ | $O(1)$||这种方法无法通过所有案例，最后几个超时|
|[剑指 Offer 22. 链表中倒数第k个节点](https://leetcode.cn/problems/lian-biao-zhong-dao-shu-di-kge-jie-dian-lcof/)|:star2:|`链表`|[1.双指针](https://leetcode.cn/submissions/detail/402038306/)<br/>|$O(n)$ | $O(1)$||可以使用双指针，快指针提前走K个，然后再一起走，快指针到达链表尾部时，返回慢指针即可|


# :four_leaf_clover: 二叉树
|**Problem**|**Difficulty**|**Tags***|**Methods****|**Time**|**Space**|**FM**|**Note**|
| --------- | :----------: |---------| ---------- | :-----: | :-----: | :--: | ------ |
|[144.二叉树前序遍历](https://leetcode.cn/problems/binary-tree-preorder-traversal/)|:star2:|`二叉树`|[1.递归](https://leetcode.cn/submissions/detail/402392301/)<br/>[2.循环](https://leetcode.cn/submissions/detail/402390893/) <br/>[3.递归(不依赖语言特性)](https://leetcode.cn/submissions/detail/403367833/)|$O(n)$<br/>$O(n)$ <br/>$O(n)$ | $O(logn)$<br/>$O(1)$ <br/>$O(n)$||前序先访问根节点，故不需要循环走到底入栈节点。只需每一步先输出根节点的值，然后判断右节点是否为空，入栈，判断左节点是否为空，入栈，进入下一次循环。1.用到了链表的合并，依赖于Python的语言特性，3.用一个全局列表避免列表的合并操作，不依赖于语言特性。|
|[144.二叉树中序遍历](https://leetcode.cn/problems/binary-tree-inorder-traversal/submissions/)|:star2:|`二叉树`|[1.递归](https://leetcode.cn/submissions/detail/402396554/)<br/>[2.循环](https://leetcode.cn/submissions/detail/402710303/)<br/> [3.Morris](https://leetcode.cn/submissions/detail/403071324/) <br/> [4.访问标记法](https://leetcode.cn/submissions/detail/403357397/)|$O(n)$<br/>$O(n)$<br/>$O(n)$<br/>$O(n)$ | $O(n)$<br/>$O(n)$<br/>$O(1)$<br/>$O(n)$||2.循环：中序根节点不会马上访问，所以需要入栈，先访问左节点，用一个指针cur指向左节点，循环一直走到其最左边，历经节点入栈，到底后开始出栈，若右节点不为空，修改cur指向右节点。需要注意的是cur不能指向已经入栈过的节点，避免死循环。3.Morris：改法改进循环法，将空间复杂度缩小为O(1)，思路是找到根节点左子树最靠右（最后一个访问）的节点，该节点的右趋节点设置为根节点，这样保证了可以回来从而顺利访问右子树。4.访问标记法：访问过的节点用黑色标记，未访问的用白色标记，若节点为白色，将其左右节点以及本身入栈（顺序依据前中后序遍历二叉树而定），若为黑色，输出值。这种方法可以用于前中后序遍历二叉树，且改动少，思路简单。|
|[104. 二叉树的最大深度](https://leetcode.cn/problems/maximum-depth-of-binary-tree/)|:star2:|`二叉树`|[1.递归](https://leetcode.cn/submissions/detail/402728358/)<br/>[2.数层数](https://leetcode.cn/submissions/detail/402733596/) <br/>[3.广度优先](https://leetcode.cn/submissions/detail/403363182/)|$O(n)$<br/>$O(n)$ <br/>$O(n)$| $O(height)$<br/>$O(n)$ <br/>$O(n)$||数层数法指的是每走一层，将该层所有非空节点存入一个列表，随后将该列表存入总列表，每一次从总列表的最后一个列表中访问内部所有节点是否有左右节点，若有，新建一个列表（新的一层），否则返回总列表的项数（即层数）。3.广度优先：思路和数层数法类似，只是每次将前一层的节点都pop掉，降低了空间复杂度为O(n)的概率|
|[543.二叉树的直径](https://leetcode.cn/problems/diameter-of-binary-tree/)|:star2:|`二叉树`|[1.递归](https://leetcode.cn/submissions/detail/403381116/)<br/>[2.]()|$O(n)$<br/>$O()$ | $O(n)$<br/>$O()$||递归方法再好好复习一下|
|[1008.前序遍历构造二叉搜索树](https://leetcode.cn/problems/construct-binary-search-tree-from-preorder-traversal/)|:star2::star2:|`二叉树`|[1.递归](https://leetcode.cn/submissions/detail/408316011/)<br/>[2.]()|$O(n)$<br/>$O()$ | $O(n)$<br/>$O()$||搜索树即左子树所有值严格小于根，右子树所有值严格大于根节点。前序遍历序列第一个值为根，所有小于该值的在左子树，大于该值的在右子树，根据这一递归思路可以求解。|
|[105. 从前序与中序遍历序列构造二叉树](https://leetcode.cn/problems/construct-binary-tree-from-preorder-and-inorder-traversal/)|:star2::star2:|`二叉树`|[1.递归](https://leetcode.cn/submissions/detail/409808626/)<br/>[2.]()|$O(n)$<br/>$O()$ | $O(n)$<br/>$O()$|||


# :deciduous_tree: 动态规划
|**Problem**|**Difficulty**|**Tags***|**Methods****|**Time**|**Space**|**FM**|**Note**|
| --------- | :----------: |---------| ---------- | :-----: | :-----: | :--: | ------ |
|[]()|:star2:|`二叉树`|[1.]()<br/>[2.]()|$O()$<br/>$O()$ | $O()$<br/>$O()$|||


# :evergreen_tree: 贪心
|**Problem**|**Difficulty**|**Tags***|**Methods****|**Time**|**Space**|**FM**|**Note**|
| --------- | :----------: |---------| ---------- | :-----: | :-----: | :--: | ------ |
|[]()|:star2:|`二叉树`|[1.]()<br/>[2.]()|$O()$<br/>$O()$ | $O()$<br/>$O()$|||


# :cactus: 回溯
|**Problem**|**Difficulty**|**Tags***|**Methods****|**Time**|**Space**|**FM**|**Note**|
| --------- | :----------: |---------| ---------- | :-----: | :-----: | :--: | ------ |
|[46. 全排列](https://leetcode.cn/problems/permutations/)|:star2::star2:|`回溯`|[1.回溯](https://leetcode.cn/submissions/detail/419087027/)<br/> [2.优化空间复杂度](https://leetcode.cn/submissions/detail/419116598/)|$O(n \cdot n!)$<br/>$O(n \cdot n!+2n)$ | $O(n \cdot n!)$<br/>$O(n \cdot n!)$||递归算法的用时和内存消耗与递归树的节点数紧密相关，递归树的非叶子结点与叶子结点的行为不同。非叶子结点中，第$i$层递归树结点数为 $A^i_{n}$ ，所以仅仅看递归树的深度，每一个叶子结点的计算用时<2n!，而每一个叶子结点中也循环了n次，所以非叶子结点的时间复杂度为 $O(n \cdot n!)$ 。最后一层有n!个叶子结点，每一个叶子结点都要进行一次拷贝，所以叶子结点的用时也为 $O(n \cdot n!)$ ,所以总的时间复杂度也为这个。对于答案数组，全排列的个数为n!，每一个需要耗费n空间，所以空间复杂度为 $O(n \cdot n!)$ ，非答案数组中，需要存储是否被访问过(n个)，以及track(长度为n)。为了减少这两个部分的空间消耗，可以直接原地对nums数组操作（官方解法，即解法2）,但是该法的缺点是结果不满足字典序。|
|[78. 子集](https://leetcode.cn/problems/subsets/)|:star2::star2:|`回溯`|[1.回溯](https://leetcode.cn/submissions/detail/420786414/)<br/> [2.二进制](https://leetcode.cn/submissions/detail/420881327/)<br/> [3.迭代法](https://leetcode.cn/submissions/detail/421516927/)<br/> [4.递归](https://leetcode.cn/submissions/detail/421527152/)<br/> [5. 二叉树遍历]()|$O(n2^n)$<br/> $O(n2^n)$<br/> $O(n2^n)$<br/> $O(n2^n)$|$O(n)$<br/> $O(n)$<br/> $O(n)$<br/> $O(n)$||使用回溯时，画出回溯树，为了不重复，每一个元素之后只访问比其大的元素，给人一种需要对nums先排序的感觉，所以我自己实现的时候对nums排序了一下，而且我递归传入backtrack函数的begin参数为begin+1，而不是i+1；标准的实现不用排序，且传入begin 参数的是i+1.对于复杂度，集合元素个数为 $2^n$ ,即状态个数，每一个状态需要 $O(n)$ 复杂度时间得到。空间复杂度为 $O(n)$ ，递归栈为 $O(n)$，临时状态空间为 $O(n)$. 方法二的二进制位思想也很好，集合的子集个数为 $2^n$ ，刚好可以用0~ $2^n-1$ 来表示，问题：如果Nums长度大于32或者64怎么办？从内存以及运行速度考虑，速度肯定慢，内存不一定存的下。方法三和方法四也很妙，两种方法思路一样，实现的方式一个使用迭代，一个用递归，核心思路是每添加一个元素，集合的子集={子集}+{子集+元素}；时间复杂度：外层是nums元素个数，内层=1+1x2+1x2x2...+ $2^n$，一共：O(n(2^{n+1}-1))=O(n2^n)；空间复杂度：不算结果列表，中间会需要将子集复制一份然后添加元素，所以为O(n),用递归方式实现的话会多一个递归栈，总的来说还是O(n)。方法5，对于每一个元素，将其状态分为选和不选，可以构成一个满二叉树，每棵树左子树表示选（或不选），右子树表示不选（或选），然后对二叉树遍历。上面说到的几种方法在[这里](https://leetcode.cn/problems/subsets/solution/er-jin-zhi-wei-zhu-ge-mei-ju-dfssan-chong-si-lu-9c/)可以学习到。|
|[39. 组合总和](https://leetcode.cn/problems/combination-sum/)|:star2::star2:|`回溯`|[1.回溯1](https://leetcode.cn/submissions/detail/422834166/)<br/> [2.官方](https://leetcode.cn/submissions/detail/423857347/)|$O(n2^n+)$<br/> [3.剪枝](https://leetcode.cn/submissions/detail/424546689/)|$O(n)$ ||回溯1是自己实现的方式，在回溯框架下，加一个检查步骤，每次加入新track前检查是否已存在，时间复杂度和空间复杂度受检查方法的影响。第二种方法注意画出回溯树更好理解，官方给出的是递归树是左子树不选，右子树选，不选的情况指针后移，选的情况指针不动，因为可能重复选。还有一个技巧是不要每一次对track.sum()，可以使用target减值然后传入，当target=0时就是一个解。画出树之后就发现每一次递归内不能有循环，如果循环了会重复。然后还可以看[这里](https://leetcode.cn/problems/combination-sum/solution/hui-su-suan-fa-jian-zhi-python-dai-ma-java-dai-m-2/)讲解解法三,解法3的思路是，先对数列表排序，每次选了之后只往后看（也看当前，因为可能重复选），这样可以防止3,2,2情况的出现。其实也可以一开始不排序，然后每次选了之后只往后看，这样和前面方法的区别在于，当遇到target-Num<0的时候，循环得用 continue，而不是break，这里的break在回溯树种体现出来的就是剪枝的效果，而continue只是搜索到了树叶。这类问题的时间复杂度如何分析？|
|[15. 3数之和](https://leetcode.cn/problems/3sum/)|:star2::star2:|`回溯`|[1.回溯超时](https://leetcode.cn/submissions/detail/424555730/)<br/> [2.优化空间复杂度](https://leetcode.cn/submissions/detail/419116598/)|$O(n \cdot n!)$<br/>$O(n \cdot n!+2n)$ | $O(n \cdot n!)$<br/>$O(n \cdot n!)$||递归算法的用时和内存消耗与递归树的节点数紧密相关，递归树的非叶子结点与叶子结点的行为不同。非叶子结点中，第$i$层递归树结点数为 $A^i_{n}$ ，所以仅仅看递归树的深度，每一个叶子结点的计算用时<2n!，而每一个叶子结点中也循环了n次，所以非叶子结点的时间复杂度为 $O(n \cdot n!)$ 。最后一层有n!个叶子结点，每一个叶子结点都要进行一次拷贝，所以叶子结点的用时也为 $O(n \cdot n!)$ ,所以总的时间复杂度也为这个。对于答案数组，全排列的个数为n!，每一个需要耗费n空间，所以空间复杂度为 $O(n \cdot n!)$ ，非答案数组中，需要存储是否被访问过(n个)，以及track(长度为n)。为了减少这两个部分的空间消耗，可以直接原地对nums数组操作（官方解法，即解法2）,但是该法的缺点是结果不满足字典序。|
|[1. 两数之和](https://leetcode.cn/problems/permutations/)|:star2:|`回溯`|[1.回溯超时](https://leetcode.cn/problems/two-sum/)<br/> [2.哈希表](https://leetcode.cn/submissions/detail/425156006/)|$O(n \cdot n!)$<br/>$O(n)$ | $O(n)$<br/>$O(n)$||使用回溯超时，但是官方的二重循环却可以通过，这个地方没有想明白为啥，回溯确实本身时间复杂度更高，但是本题中结果列表长度一旦=2就停止继续往下递归，每选取一个数就会继续看这个数的后面是否有数使得结果列表满足要求，所以按理来说两种方法用时一样的。哈希表法的核心思想：将列表的前一部分的补集和该数的索引存入哈希表，等到后面遇到这个数的补集时，直接根据哈希表查找补集的补集的索引|

