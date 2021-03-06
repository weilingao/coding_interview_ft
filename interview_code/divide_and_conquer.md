# 分治策略
>[](#),


[Leetcode Q215](java_src/215.数组中的第K个最大元素.java) 数组中的第K个最大元素
```
1. 优先队列：保持优先队列只有k个小的元素
2. 基于快速排序的选择方法（边排序边查找）：
我们可以用快速排序来解决这个问题，先对原数组排序，再返回倒数第k个位置，这样平均时间复杂度是O(nlogn)，但其实我们可以做的更快。

首先我们来回顾一下快速排序，这是一个典型的分治算法。我们对数组a[l⋯r] 做快速排序的过程是：

分解： 将数组a[l⋯r] 「划分」成两个子数组 a[l⋯q−1]、a[q+1⋯r]，使得 a[l⋯q−1] 中的每个元素小于等于 a[q]，且 a[q] 小于等于a[q+1⋯r] 中的每个元素。其中，计算下标 qq 也是「划分」过程的一部分。
解决： 通过递归调用快速排序，对子数组 a[l⋯q−1] 和 a[q+1⋯r] 进行排序。
合并： 因为子数组都是原址排序的，所以不需要进行合并操作，a[l⋯r] 已经有序。
上文中提到的 「划分」 过程是：从子数组 a[l⋯r] 中选择任意一个元素 x 作为主元，调整子数组的元素使得左边的元素都小于等于它，右边的元素都大于等于它，x 的最终位置就是 q。
由此可以发现每次经过「划分」操作后，我们一定可以确定一个元素的最终位置，即 x 的最终位置为 qq，并且保证 a[l⋯q−1] 中的每个元素小于等于 a[q]，且 a[q] 小于等于 a[q+1⋯r] 中的每个元素。所以只要某次划分的 q 为倒数第 k 个下标的时候，我们就已经找到了答案。 我们只关心这一点，至于 a[l⋯q−1] 和 a[q+1⋯r] 是否是有序的，我们不关心。
因此我们可以改进快速排序算法来解决这个问题：在分解的过程当中，我们会对子数组进行划分，如果划分得到的 q 正好就是我们需要的下标，就直接返回 a[q]；否则，如果 q 比目标下标小，就递归右子区间，否则递归左子区间。这样就可以把原来递归两个区间变成只递归一个区间，提高了时间效率。这就是「快速选择」算法。
```