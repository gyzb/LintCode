#问题(交叉字符串)

给出三个字符串:s1、s2、s3，判断s3是否由s1和s2交叉构成。

#举例
####例 1:
    输入:
    "aabcc"
    "dbbca"
    "aadbbcbcac"
    输出:
    true
####例 2:
    输入:
    ""
    ""
    "1"
    输出:
    false
####例 3：
    输入:
    "aabcc"
    "dbbca"
    "aadbbbaccc"
    输出:
    false



#挑战
O(log(n) + log(m)) 时间复杂度