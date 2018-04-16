## 问题分析：
 给定二进制数组，找到该数组中连续1的最大数.
  
## 编程实现： 
```c++class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int res = 0, cnt = 0;
        for (int num : nums) {
            cnt = (num == 0) ? 0 : cnt + 1;
            res = max(res, cnt);
        }
        return res;
    }
};  
```
## 总结体会：
用一个计数器cnt来统计1的个数，如果当前数字为0，那么cnt重置为0，如果不是0，cnt自增1，然后每次更新结果res.
