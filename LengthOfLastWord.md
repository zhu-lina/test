## 问题分析：
  给定一个字符串， 包含大小写字母、空格 ' '，请返回其最后一个单词的长度.如果不存在最后一个单词，请返回 0 .
  
## 编程实现： 
```c++
class Solution {  
public:
    int lengthOfLastWord(string s) {  
        int len = s.length();  
        int t = 0;  
        for(int i = len-1 ; i >= 0 ; i --) {  
            if(s[i] == ' ')  continue;  
            while(s[i-t] != ' '&&i-t >= 0) {  
               t++;  
            }  
            return t;  
        }  
        return t;  
    }  
};  
```
## 总结体会：
主要关心的是非空格字符，在遍历字符串的时候，如果遇到非空格的字符，我们只需要判断其前面一个位置的字符是否为空格再进行操作.
