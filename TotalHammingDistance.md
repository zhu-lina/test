## 问题分析：
两个整数之间的汉明距离是相应位不同的位置数。现在你的工作是找出所有给定数字对之间的总汉明距离。
## 编程实现：
```c++
class Solution {
public:
    int totalHammingDistance(vector<int>& nums) {
          int result = 0, n = nums.size();
        for(int i = 0; i < 32; i++) {
            int cnt = 0;
            for(int j = 0; j < n; j++) {
                if(nums[j] >> i & 1 == 1)
                    cnt++;
            }
            result += cnt * (n - cnt);
        }
        return result;
    }
};
```
## 总结体会：
遍历数组中所有数的相同某位，如果有cnt个1，n-cnt个0，则这一位能够构成的Hamming距离为cnt * (n - cnt)所以从第0位开始一直计算到第32位，将所有位贡献的Hamming距离总和相加即可得到总的Hamming距离。