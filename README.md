# dqx_code_nowcoder
最近一直在刷题，还是记录一下好整理



## 5.7



q1:[图片整理_牛客题霸_牛客网 (nowcoder.com)](https://www.nowcoder.com/practice/2de4127fda5e46858aa85d254af43941?tpId=37&tqId=21257&rp=1&ru=/exam/oj/ta&qru=/exam/oj/ta&sourceUrl=%2Fexam%2Foj%2Fta%3FtpId%3D37&difficulty=undefined&judgeStatus=undefined&tags=&title=)

思路：简单的排序问题，将char扔进去一个string中，对这个string进行排序得到结果

直接使用`<algorithm>`库中的快排函数进行排序

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    string str;
    cin >> str;
    sort(str.begin(), str.end());
    cout << str;
}

```

代码很简单，使用了`sort`函数的时间复杂度是`O(n*log(n))`，空间复杂度为`O(n)`



q2:[明明的随机数_牛客题霸_牛客网 (nowcoder.com)](https://www.nowcoder.com/practice/3245215fffb84b7b81285493eae92ff0?tpId=37&tqId=21226&rp=1&ru=/exam/oj/ta&qru=/exam/oj/ta&sourceUrl=%2Fexam%2Foj%2Fta%3FtpId%3D37&difficulty=undefined&judgeStatus=undefined&tags=&title=)

思路：用set去重就好了，也很简单

```c++
#include <bits/stdc++.h>
using namespace std;

int main(){
    int n,temp;
    cin>>n;
    set<int> s;
    for(int i=0;i<n;i++){
        cin>>temp;
        s.insert(temp);
    }
    for (const auto &u : s) {
        cout << u << endl;
    }
}
```

代码很简单，但是有几个值得注意的点：

1. 使用const auto &u来做可以减少拷贝（其为一个对集合s中的元素的引用）

2. set为标准库中的一个容器，`set` 使用元素的 `<` 操作符对元素进行排序。对于整数（`int` 类型），这意味着元素将按照从小到大的顺序排列。在这个程序中，我们使用 `set<int>`，所以插入元素时，`set` 会自动进行排序。当我们遍历 `set` 时，元素会按照已排序的顺序输出。

3. 时空复杂度分析：

   ​      插入操作的时间复杂度为 O(log n)，其中 n 为集合中元素的数量。这是因为 `set` 底层通常使用`平衡二叉搜索树`（例如红黑树）实现，其搜索、插入和删除操作的时间复杂度均为` O(log n)`。在这个程序中，最多插入 *n* 个元素，因此插入操作的总时间复杂度为`O(nlogn)`。遍历 `set` 的时间复杂度为 `O(n)`，因为我们需要访问集合中的每个元素。综合考虑，程序的总时间复杂度为`O(nlogn)`。

   ​      程序的主要空间开销来自 `set` 容器。在最坏的情况下（没有重复的数字），`set` 中会存储 *n* 个不同的整数。因此，空间复杂度为 O(n)。



q3:[计算某字符出现次数_牛客题霸_牛客网 (nowcoder.com)](https://www.nowcoder.com/practice/a35ce98431874e3a820dbe4b2d0508b1?tpId=37&tqId=21225&rp=1&ru=/exam/oj/ta&qru=/exam/oj/ta&sourceUrl=%2Fexam%2Foj%2Fta%3FtpId%3D37&difficulty=undefined&judgeStatus=undefined&tags=&title=)

question:写出一个程序，接受一个由字母、数字和空格组成的字符串，和一个字符，然后输出输入字符串中该字符的出现次数。（不区分大小写字母）

思路：使用transform将所有的字母统一转化为小写，使用count对这些字母进行计数分析

```c++
#include <bits/stdc++.h>
using namespace std;

int main() {
    string str;
    getline(cin,str);
    char b = tolower(getchar());
    transform(str.begin(),str.end(),str.begin(),::tolower);
    cout<<count(str.begin(),str.end(),b);
}

```

`transform` 对字符串 `a` 的所有元素执行 `tolower` 函数，将大写字母转换为小写字母。`a.begin()` 和 `a.end()` 分别表示字符串 `a` 的开始和结束迭代器。`a.begin()` 作为输出迭代器意味着转换后的元素将被直接写回 `a`。

时间复杂度为O(n)，空间复杂度为O(1);



q4:[购物单_牛客题霸_牛客网 (nowcoder.com)](https://www.nowcoder.com/practice/f9c6f980eeec43ef85be20755ddbeaf4?tpId=37&tqId=21239&rp=1&ru=/exam/oj/ta&qru=/exam/oj/ta&sourceUrl=%2Fexam%2Foj%2Fta%3Fpage%3D1%26pageSize%3D50%26search%3D%26tpId%3D37%26type%3D37&difficulty=undefined&judgeStatus=undefined&tags=&title=)

一眼DP，怎么构造状态转移方程是关键

```c++
```



