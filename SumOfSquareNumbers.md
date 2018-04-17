## 问题分析：
#### 给定一个非负整数 c ，你要判断是否存在两个整数 a 和 b，使得 a^2 + b^2 = c.
## 编程实现：
```C++
class Solution {
public:
    bool judgeSquareSum(int c) {
        for(int i=0,j=sqrt(c);i<=j;){  
            int tmp=i*i+j*j;  
            if(tmp<c){  
                i++;  
                continue;  
            }if(tmp>c){  
                j--;  
                continue;  
            }  
            if(tmp==c){  
                return true;  
            }  
        }  
        return false;  
    }  
};  
        
```
## 总结体会：
#### 将输入的平方和的值与非负整数c的大小进行比对，若相等，则输出true，否则，输出false。还利用了for循环语句和if语句。


