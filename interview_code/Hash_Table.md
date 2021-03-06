## Hash_Table
[Leetcode Q3](java_src/3.无重复字符的最长子串.java) Longest Substring Without Repeating Characters (无重复字符的最长子串)
> ByteDance, Huawei
```
Using sliding window and hashset to find substring without repeating characters starting from each index, find the largest length
```

[Leetcode Q409](java_src/409.最长回文串.java) 最长回文串
```
回文串是一个正着读和反着读都一样的字符串。以回文中心为分界线，对于回文串中左侧的字符 ch，在右侧对称的位置也会出现同样的字符。例如在字符串 "abba" 中，回文中心是 "ab|ba" 中竖线的位置，而在字符串 "abcba" 中，回文中心是 "ab(c)ba" 中的字符 "c" 本身。我们可以发现，在一个回文串中，只有最多一个字符出现了奇数次，其余的字符都出现偶数次。

那么我们如何通过给定的字符构造一个回文串呢？我们可以将每个字符使用偶数次，使得它们根据回文中心对称。在这之后，如果有剩余的字符，我们可以再取出一个，作为回文中心。

对于每个字符 ch，假设它出现了 v 次，我们可以使用该字符 v / 2 * 2 次，在回文串的左侧和右侧分别放置 v / 2 个字符 ch，其中 / 为整数除法。例如若 "a" 出现了 5 次，那么我们可以使用 "a" 的次数为 4，回文串的左右两侧分别放置 2 个 "a"。

如果有任何一个字符 ch 的出现次数 v 为奇数（即 v % 2 == 1），那么可以将这个字符作为回文中心，注意只能最多有一个字符作为回文中心。在代码中，我们用 ans 存储回文串的长度，由于在遍历字符时，ans 每次会增加 v / 2 * 2，因此 ans 一直为偶数。但在发现了第一个出现次数为奇数的字符后，我们将 ans 增加 1，这样 ans 变为奇数，在后面发现其它出现奇数次的字符时，我们就不改变 ans 的值了。
```

[Leetcode Q448](java_src/448.找到所有数组中消失的数字.java) 找到所有数组中消失的数字
```
见代码
```

[Leetcode Q49](java_src/49.字母异位词分组.java) 49.字母异位词分组
```
    // 本题思路：
    // 每个字符串排序作为key，依次加入map
    // 直接输出每个key对应的字母异位词list即可
```

[Leetcode Q169](java_src/169.多数元素.java) 169.多数元素
```
    // 本题思路：
    // 遍历数组，维持map，数组元素和元素出现次数的映射，保持出现最大次数及相对应的元素
```

[剑指Offer56-I](java_src/剑指Offer56-I数组中数字出现的次数.java) 剑指Offer56-I数组中数字出现的次数
```
    // 本题思路：
    // 哈希表，记录元素和出现次数，遍历就完事了
```

[Leetcode Q128](java_src/128.最长连续序列.java) 128.最长连续序列
```
    // 本题思路：
    // 只有当一个数是连续序列的第一个数的情况下才会进入内层循环，然后在内层循环中匹配连续序列中的数，
    // 因此数组中的每个数只会进入内层循环一次。根据上述分析可知，总时间复杂度为 O(n)
```

[剑指Offer03](java_src/剑指Offer03.数组中重复的数字.java) 剑指Offer03.数组中重复的数字
```
    // 本题思路：
    // 用set
```

[剑指Offer50](java_src/剑指Offer50.第一个只出现一次的字符.java) 剑指Offer50.第一个只出现一次的字符
```
    // 本题思路：
    // 在哈希表的基础上，有序哈希表中的键值对是 按照插入顺序排序 的。基于此，可通过遍历有序哈希表，实现搜索首个 “数量为 1 的字符”。
```