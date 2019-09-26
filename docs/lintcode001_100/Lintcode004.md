#问题(丑数 II)

设计一个算法，找出只含素因子`2`，`3`，`5` 的第 n 小的数。  
符合条件的数如：`1, 2, 3, 4, 5, 6, 8, 9, 10, 12...`

    ！ 我们可以认为 1 也是一个丑数。

#举例
####例 1:
    输入：9
    输出：10
####例 2:
    输入：1
    输出：1

#挑战
要求时间复杂度为 O(nlogn) 或者 O(n)。    
    
    
##算法代码
C++
```buildoutcfg
class Solution {
public:
    /**
     * @param n: An integer
     * @return: return a  integer as description.
     */
    int min(int a, int b)
    {
        return a < b ? a : b;
    }
    int nthUglyNumber(int n) {
        // write your code here
        if(n == 1)
        {
            return n;
        }
        std::vector<int> ugly;
        ugly.push_back(1);
        int t2 = 0;
        int t3 = 0;
        int t5 = 0;
        for(int i = 1; i < n; i++)
        {
            ugly.push_back(min(min(ugly[t2]*2, ugly[t3]*3), ugly[t5]*5));
            if(ugly[i]/ugly[t2] == 2)
            {
                t2++;
            }
            if(ugly[i]/ugly[t3] == 3)
            {
                t3++;
            }
            if(ugly[i]/ugly[t5] == 5)
            {
                t5++;
            }
        }
        return ugly.back();
    }
};
```
Python

```buildoutcfg
class Solution:
    """
    @param n: An integer
    @return: return a  integer as description.
    """
    def nthUglyNumber(self, n):
        # write your code here
        if n == 1:
            return n
        ugly = [1]
        t2 = 0
        t3 = 0
        t5 = 0
        for i in range(1,n):
            ugly.append(min(min(ugly[t2]*2, ugly[t3]*3), ugly[t5]*5))
            if ugly[i]//ugly[t2] == 2:
                t2 += 1
            if ugly[i]//ugly[t3] == 3:
                t3 += 1
            if ugly[i]//ugly[t5] == 5:
                t5 += 1
        return ugly[-1]
```
