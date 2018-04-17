## 问题分析：
####
给定字符串 J 代表你现在拥有代表宝石的类型，和字符串 S 代表你拥有的石头。S 中每个字符代表了一种你拥有的石头的类型，你想知道你拥有的石头中有多少是宝石。

J 中的字母不重复，J 和 S 中的所有字符都是字母。字母区分大小写，因此"a"和"A"是不同类型的石头。
## 编程实现：
```c++
class Solution {
public:
    int numJewelsInStones(string J, string S) 
    {
        int i = 0;
        for(int j=0; j<J.length(); j++) {
            for(int s=0; s<S.length(); s++) {
                if(J[j] == S[s]) i++;
            }
        }
        return i;
    }
  }；
```
## 总结体会：
通过该程序可以实现拥有的石头有多少是宝石，利用了循环结构和if语句进行判断，还利用了函数的声明。
