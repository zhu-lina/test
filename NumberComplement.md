## 问题分析：
####
给定一个正整数，输出其补数。 补码策略是翻转其二进制表示的位.
## 编程实现：
```c++
class Solution {
public:
    int findComplement(int num) {
          int t = 0;
        if(num == 0)
            return 1;
        int c = 1;
        while(num != 0)
        {
            int a = num%2;
            int b = a>0?0:1;
            t += b*c;
            c *=2;
            num = num / 2;
        }
        return t;
    }
    
}; 
```
## 总结体会：
通过该程序可以实现拥有的石头有多少是宝石，利用了循环结构和if语句进行判断，还利用了函数的声明。
