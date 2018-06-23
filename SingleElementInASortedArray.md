## 问题分析：
给定一个只包含整数的排序数组，每个元素出现两次，除了一次出现的元素之外。 找到仅出现一次的单个元素。
## 编程实现：
```c++
class Solution {
public:
    int singleNonDuplicate(vector<int>& nums) {
        if(nums.size() == 1)
        return nums[0];
    if(nums[0] != nums[1])
        return nums[0];
    if(nums[nums.size()-1] != nums[nums.size()-2])
        return nums[nums.size()-1];
    int l = 0, r = nums.size()-1;

    while(l <= r)
    {
        int mid = (l+r)/2;
        if(nums[mid]!=nums[mid-1] && nums[mid]!=nums[mid+1])
            return nums[mid];
        if(nums[mid] == nums[mid+1])
        {
            if((mid-l) % 2 == 1)
                r = mid-1;
            else
                l = mid+2;
        }
        else if(nums[mid] == nums[mid-1])
        {
            if((mid-l-1) % 2 == 1)
                r = mid-2;
            else
                l = mid+1;
        }
    }
 
    }
};
```
## 总结体会：
采用二分查找,由于总元素个数为奇数个,可以将数组分为左右两部分,然后答案在奇数子数组中。