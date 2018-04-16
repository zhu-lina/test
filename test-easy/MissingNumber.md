## 问题分析：
####
给定一个包含从0,1,2，...，n中取出的n个不同数字的数组，找到数组中缺少的数字。
## 编程实现：
```c++
class Solution {
public:
    int missingNumber(vector<int>& nums) {
           int n = nums.size();  
        int t = n;  
        for(int i = 0;i < n;i++){  
            t ^= i;  
            t ^= nums[i];  
        }  
        return t;  
    }  
    };
```
## 总结体会：
用异或操作符，两个相同的数异或等于0，与0异或等于自身的思想.
