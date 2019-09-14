# 1.两数之和
&emsp;&emsp;建立一个字典，键为具体值，值为数字列表用来存储同一数字的不同位置。然后依次检查目标值减去数组的个体值的键值是否存在，并加入同个数字情况的判断。  
&emsp;&emsp;建立字典进行查询以获得 O(n) 复杂度。
<br/>
<br/>
<br/>

# 2.两数相加
&emsp;&emsp;通过对 10 求余以及除获得当前结点值以及是否需要进行进位。分三种情况并在最后对最后一次进位的判断。  
&emsp;&emsp;理论上为 O(max(m,n)) 复杂度。
<br/>
<br/>
<br/>

# 3.无重复字符的最长子串
&emsp;&emsp;建立一个128长的数组，因为 A-z 的 ASCII 码在 65-127 之间，且 128 为 2 的幂。然后将字符串的每个字符映射到数组中，通过记录每个字符在上一次出现时的位置来确定最长子串的长度。  
&emsp;&emsp;15 行中的 i+1 用于记录实际的数字位置，用来通过只包含一个字符的测试用例。
<br/>
<br/>
<br/>

# 4.寻找两个有序数组的中位数
&emsp;&emsp;插入排序。<br/><br/>
&emsp;&emsp;2.0 版本特化了对中位数查询，将长度设置为了特定的长度。<br/><br/>
&emsp;&emsp;3.0 版本想到根本不需要这么长的数组浪费空间，分情况建立一个长度为 2 以及长度为 1 的数组，运行到总长度的一半跳出循环，最后直接取数组的平均值。
<br/>
<br/>
<br/>

# 5.最长回文子串
&emsp;&emsp;平平无奇的暴力查找，直接分为奇偶两种情况进行讨论。<br/><br/>
&emsp;&emsp;1.0 版本采用了在每个字母前后添加字符的做法，然而感觉比分奇偶的情况要慢很多。  
<br/>
<br/>

# 6. Z 字形变换
&emsp;&emsp;平平无奇的找规律。已知每间隔 interval=(2\*numRows-2) ，先对下标对 interval 进行求余获得 x ，然后通过 x 和 (interval-x) 之间的最小值确定相应的字符具体位于哪一行。  
&emsp;&emsp;时间复杂度和空间复杂度都为 O(n)
<br/>
<br/>
<br/>

# 7. 整数反转
&emsp;&emsp;用 Int64 进行计算，然后根据结果是否大于 int 最大值或小于 int 最小值返回 0，否则进行强制类型转换对 Int64 值进行截断返回 int 类型值。  
&emsp;&emsp;时间复杂度为 O(n)，n 为输入数字的位数。空间复杂度为 O(1)。
<br/>
<br/>
<br/>

# 8. 字符串转换整数 (atoi)  
&emsp;&emsp;v1.0 使用正则表达式，然而正则表达式不在基础库中，在 LeetCode 中会编译失败。python 倒是可以用正则。<br/><br/>
&emsp;&emsp;v2.0 这里实现了两个状态机，首先在遇到 +、-、以及数字时跳出第一个状态机。然后在遇到非数字时跳出第二个状态机。随后通过异常块，捕获 OverflowException 返回最大最小值。捕获其他异常返回 0 。剩下的正常情况就返回原值。<br/><br/>
&emsp;&emsp;v3.0 由于一开始考虑使用正则，但不在类库中想实现状态机，发现自己被一开始的想法绕了进去，重新思考后选择通过除符号位外的字符通过 ASCII 码获取其真实数字值。通过 Int64 截断前后的值判断对于 32 位的 int 是否溢出而判断是返回强制类型转换后的值还是 int.MaxValue 或者 int.MinValue。
<br/>
<br/>
<br/>

# 9. 回文数
&emsp;&emsp;平平无奇的题目
<br/>
<br/>
<br/>

# 10. 正则表达式匹配
&emsp;&emsp;通过动态规划，此处使用自顶向下进行解答。首先将最后一行除最后一个元素的元素置为 false ，判断是否存在 * 字符从而分情况进行迭代。
<br/>
<br/>
<br/>

# 11. 盛最多水的容器
&emsp;&emsp;两边依次向中间递归，只考虑短边向中间递归即可。  
&emsp;&emsp;时间复杂度 O(n)，空间复杂度 O(1)。
<br/>
<br/>
<br/>

# 12. 整数转罗马数字
&emsp;&emsp;v1.0，通过函数建立表进行检索，时间复杂度 O(n)，n为总的符号数，但常数项很大。且需要同样很大常数项的空间复杂度 O(n)。<br/><br/>
&emsp;&emsp;v2.0 通过手动建立表，和 1.0 旗鼓相当。<br/><br/>
&emsp;&emsp;v3.0，通过找规律建立 switch ，时间复杂度为 O(lg(n))，n 为输入数字的大小。空间复杂度为 O(m)，m 为总的符号数。
<br/>
<br/>
<br/>

# 13. 罗马数字转整数
&emsp;&emsp;建立字典进行查询，考虑到罗马数字的组成若前一个数字比后一个要小即减去，得到基本算式。然后在循环中通过在循环开始对 next 赋值，结束时对 pre 赋值，对两者进行对比从而分情况进行计算。
<br/>
<br/>
<br/>

# 14. 最长公共前缀
&emsp;&emsp;对每次假定的公共前缀依次进行比较，然后取最后相等的位置获得新的公共前缀。<br/>
&emsp;&emsp;时间复杂度 O(n),空间复杂度 O(m)，m 为公共前缀的长度。虽然可以将空间复杂度降低为 O(1) 即只通过索引对第一个字符串的各个字符进行比较，但为了可读性进行妥协。
<br/>
<br/>
<br/>
