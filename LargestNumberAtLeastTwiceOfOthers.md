## 问题分析：
#### 在给定的整数数组nums中，始终只有一个最大的元素。查找数组中最大的元素是否至少是数组中第二大数的两倍.如果是，返回最大元素的索引，否则返回-1.
## 编程实现：
```c++
class Solution {
public:
    int dominantIndex(vector<int>& nums) {
          if(nums.size()==1)  
            return 0;  
        int max1=nums[0],max2=0;  
        int index=0;  
        for(int i=0;i<nums.size();i++)  
        {  
            if(nums[i]>=max1)  
            {  
                max1=nums[i];  
                index=i;  
            }  
        }  
        for(int i=0;i<nums.size();i++)  
        {  
            if(i!=index&&nums[i]>max2)  
                max2=nums[i];  
        }  
        if(max2==0)  
            return index;  
        else  
        {  
            if(max1/max2>=2)  
                return index;  
            else  
                return -1;  
        }  
    }  
};  
```
## 总结体会：
#### 程序中使用了if语句和for循环，先找到最大的数字，再找到第二大的数字，再将其判断两数是否多于2倍.
