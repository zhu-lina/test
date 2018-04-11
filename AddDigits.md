## 问题分析：
#### 给出一个非负整数 num，反复的将所有位上的数字相加，直到得到一个一位的整数。
## 编程实现：
```C++
class Solution {
public:
    int addDigits(int num) {
              int sum = 0;  
    int Num = 0;  
    while(1) {  
        while(num) {  
            Num = num%10;  
            sum += Num;  
            num /=10;  
        }  
        if(sum<10) {  
            break;  
        }  
        num = sum;  
        sum = 0;  
    }  
    return sum;  
}  
};
```
## 总结体会：
#### 在编程过程中，必须考虑while语句跳出时刻的值，再进行判断看是否大于10 ，进而再将其输出，也使用了if-else语句。
