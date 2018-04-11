
## 问题分析：
#### 实现 int sqrt(int x) 函数，计算并返回 x 的平方根。
    x保证是一个非负整数。
## 编程实现：
```C++
class Solution {
public:
    int mySqrt(int x) {
        int low = 0, high = 46341, mid = 0;

        while(low <= high) { 
            if (mid == low + (high-low)/2) {  
                break;  
            } 
            mid = low + (high-low)/2;
            int square = mid * mid;

            if(square == x) {
                return mid;
            }
            else if(x > square){
                low =  mid;
            }
            else {
                high = mid;
            }
        }
        return mid;
    }
};
        
```
## 总结体会：
采用二分法的思想，将 mid*mid 的值与 x 比较，但为了防止计算平方时发生溢出，二分上限为 46341 而非 x 的值。
又因为待求数的平方根有可能是介于两个整数之间的，这种情况需要做一下判断处理，否则会陷入死循环中。

