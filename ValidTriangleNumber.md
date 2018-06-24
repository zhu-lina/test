## 问题分析：
给定一个由非负整数组成的数组，您的任务是计算从数组中选择的三元组的数量，如果我们将它们作为三角形的边长，可以生成三角形。
## 编程实现：
```c++
class Solution {
public:
    int triangleNumber(vector<int>& nums) {
        int res = 0;
        sort(nums.begin(), nums.end());
        for (int i = nums.size() - 1; i >= 2; i--)
        {
            int left = 0, right = i - 1;
            while (left <= right)
            {
                if (nums[left] + nums[right] > nums[i])
                {
                    res += (right - 1 - left + 1);
                    right--;
                }
                else
                    left++;
            }
        }
        return res;
    }
};
```
## 总结体会：
排序之后，从数字末尾开始往前遍历，将left指向首数字，将right之前遍历到的数字的前面一个数字，然后如果left小于right就进行循环，循环里面判断如果left指向的数加上right指向的数大于当前的数字的话，那么right到left之间的数字都可以组成三角形相当于此时确定了i和right的位置，可以将left向右移到right的位置，中间经过的数都大于left指向的数，所以都能组成三角形，加完之后，right自减一，即向左移动一位。如果left和right指向的数字之和不大于nums[i]，那么left自增1，即向右移动一位.