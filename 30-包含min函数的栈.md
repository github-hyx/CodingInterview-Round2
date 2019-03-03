# 30-包含min函数的栈

[OJ链接](https://www.nowcoder.com/practice/4c776177d2c04c2494f2555c9fcc1e49?tpId=13&tqId=11173&tPage=1&rp=1&ru=%2Fta%2Fcoding-interviews&qru=%2Fta%2Fcoding-interviews%2Fquestion-ranking)

**题目描述**

定义栈的数据结构，请在该类型中实现一个能够得到栈中所含最小元素的min函数（时间复杂度应为O（1））。

**思路分析**

**代码实现（思路一）**

```c++
class Solution 
{
public:
    void push(int value) 
    {
        s1.push(value);
        if(s2.empty()||value<=s2.top())
            s2.push(value);
        else
            s2.push(s2.top());
    }
    void pop() 
    {
        s1.pop();
        s2.pop();
    }
    int top() 
    {
        return s1.top();
    }
    int min() 
    {
        return s2.top();
    }
private:
    stack<int> s1,s2;
};
```

**总结**

* 注意s2为空的情况



