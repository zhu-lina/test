## 问题分析：

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
 其中二进制转换为十进制用 y=a0* 2^0 +a1* 2^1 +a2* 2^2 +a3* 2^3 +a4* 2^4 + … ， 2的n次方在代码中用c来表示，b用三目运算符直接翻转其二进制表示的位.
采用了while循环语句.
