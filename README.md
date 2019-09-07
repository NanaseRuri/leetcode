# 1.两数之和
&emsp;&emsp;建立一个字典，键为具体值，值为数字列表用来存储同一数字的不同位置。然后依次检查目标值减去数组的个体值的键值是否存在，并加入同个数字情况的判断。  
&emsp;&emsp;建立字典进行查询以获得O(n)复杂度。  


# 2.两数相加
&emsp;&emsp;通过对10求余以及除获得当前结点值以及是否需要进行进位。分三种情况并在最后对最后一次进位的判断。  
&emsp;&emsp;理论上为O(max(m,n))复杂度。  


# 3.无重复字符的最长子串
&emsp;&emsp;建立一个128长的数组，因为A-z的ASCII码在65-127之间，且128为2的幂。然后将字符串的每个字符映射到数组中，通过记录每个字符在上一次出现时的位置来确定最长子串的长度。  
&emsp;&emsp;15行中的i+1用于记录实际的数字位置，用来通过只包含一个字符的测试用例。  


# 3.寻找两个有序数组的中位数
&emsp;&emsp;插入排序。  
&emsp;&emsp;2.0版本特化了对中位数查询，将长度设置为了特定的长度。  
&emsp;&emsp;3.0版本想到根本不需要这么长的数组浪费空间，分情况建立一个长度为2以及长度为1的数组，运行到总长度一般跳出循环，最后直接取数组的平均值。
