#问题(统计数字)

计算数字 k 在 0 到 n 中的出现的次数，k 可能是 0~9 的一个值。


#举例
####例 1:
    输入：k = 1, n = 1
    输出：1
    解释：在 [0, 1] 中，我们发现 1 出现了 1 次 (1)。
####例 2:
    输入：k = 1, n = 12
    输出：5
    解释：在 [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12] 中，我们发现 1 出现了 5 次 (1, 10, 11, 12)(注意11中有两个1)。


******
<font color=#0099ff size=12 face="黑体">开始解题</font>

首先要确定，k的取值范围是0-9，因此只要一个数对10进行取余操作就可以得到最后一位并且取值范围在0-9。`需要一个取余变量rem。`  
又因为n值范围不确定，位数不确定，所以需要一个变量保存除以10之后的商。`需要一个取商变量quo。`  
我们要给数组（或者列表）的每一个数字数k值出现的次数，所以我们整个数组（或者列表）全部遍历一次。`需要一个for循环。`  
最后需要一个结果变量保存结果并返回。`需要一个结果result。`


##算法逻辑
确定了算法需要的变量，剩下的就是对变量进行逻辑组合。<font color=#ff99ff size=4 face="黑体">千万不要觉得算法逻辑最重要，有时候确定需要的变量比算法逻辑更重要！</font>

    第一步，确定k值和n值的大小关系。显然如果k值大于n值意味着在0-n的范围内还不曾出现k，所以当k大于n时返回值为0；
    第二步，将取余结果与k值进行比较，如果相等，结果变量便加一。顺便使用quo保存除以10后的商值（整数）。
    第三步，两位数及以上的要对第二步的商重新取余，更新rem值，然后重复第二步，直到只剩一位，即商值为0。
    第四步，返回result结果变量。

##算法代码
C++
```buildoutcfg
class Solution {
public:
    /**
     * @param k: An integer
     * @param n: An integer
     * @return: An integer denote the count of digit k in 1..n
     */
    int digitCounts(int k, int n) {
        // write your code here
        if(k > n)
        {
            return 0;
        }
        int result = 0;
        for(int i = 0; i<=n; i++)
        {
            int rem = i % 10;
            int quo = i / 10;
            if(k == rem)
            {
                result++;
            }
            while(quo)
            {
                rem = quo % 10;
                quo = quo / 10;
                if(k == rem)
                {
                    result++;
                }
            }
        }
        return result;
    }
};
```
Python

```buildoutcfg
class Solution:
    """
    @param k: An integer
    @param n: An integer
    @return: An integer denote the count of digit k in 1..n
    """
    def digitCounts(self, k, n):
        # write your code here
        if k > n:
            return 0
        result = 0
        for i in range(n+1):
            rem = i % 10
            quo = i // 10
            if k == rem:
                result += 1
            while quo:
                rem = quo % 10
                quo = quo // 10
                if k == rem:
                    result += 1
        return result

```