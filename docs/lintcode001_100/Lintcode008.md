#问题(旋转字符串)

给定一个字符串（以字符数组的形式给出）和一个偏移量，根据偏移量`原地`旋转字符串(从左向右旋转)。

    ！offset >= 0   str的长度 >= 0
#举例
####例 1:
    输入:  str="abcdefg", offset = 3
    输出:  str = "efgabcd"	
    样例解释:  注意是原地旋转，即str旋转后为"efgabcd"
####例 2:
    输入: str="abcdefg", offset = 0
    输出: str = "abcdefg"	
    样例解释: 注意是原地旋转，即str旋转后为"abcdefg"
####例 3：
    输入: str="abcdefg", offset = 1
    输出: str = "gabcdef"	
    样例解释: 注意是原地旋转，即str旋转后为"gabcdef"
####例 4：
    输入: str="abcdefg", offset =2
    输出: str = "fgabcde"	
    样例解释: 注意是原地旋转，即str旋转后为"fgabcde"
####例 5：
    输入: str="abcdefg", offset = 10
    输出: str = "efgabcd"	
    样例解释: 注意是原地旋转，即str旋转后为"efgabcd"
 
#挑战
在数组上原地旋转，使用O(1)的额外空间



