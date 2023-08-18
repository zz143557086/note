#include<algorithm>

1.排序函数sort(数组名+n1，数组名+n2)将n1到n2的元素从小到大排列

n1和n2都是int类型的表达式，可以包含变量

如果n1=0，则+n1可以不写

sort(数组名+n1，数组名+n2,greater<T>());将类型为T的元素从大到小排序

sort(数组名+n1，数组名+n2，排序规则结构名（）)

* **排序规则结构的定义如下：**

struct{

bool operator()( const **T** &a1,const **T** & a2) const {

a1<a2表示a1在a2前面 

}

}a1在a2前面返回turn 后面返回false    加粗的为你规定的

2.1 二分查找 binary_search(数组名+n1，数组名+n2，值)从小到大的查找[n1,n2) 

查找等于值<=>  找到那个值返回ture 没找到返回false

2.2 binary_search(数组名+n1，数组名+n2，值，排序规则结构名 同上sort类似)

2.3 lower_bound(数组名+n1,数组名+n2,值) 返回值是 T * p  从小到大

*p是查找区间里下标最小的，大于等于“值”的元素如果找不到，p指向小标为n2的元素

2.4 lowe_bound(数组名+n1,数组名+n2,值,排序规则结构名 同上sort) 

2.5 upper_bound(数组名+n1,数组名+n2,值) 从小到大

*p是查找区间里下标最小，大于“值的元素”如果找不到，p指向小标为n2的元素

2.6 upper_bound(数组名+n1,数组名+n2,值,排序规则结构名 同上sort) 

3.1 头文件#include<set>平衡二叉树数据结构 multiset

multiiset<T> st;

定义一个multiset变量为st，st里面可以存放t类型数据，并且能自动排序，开始是st为空

排序规则：表达式 “  a<b ” 为turn ，则a排在b前面

可用 st.insert添加元素，st.find查找元素，st.erase删除元素，复杂度都是log（n）

**3.* 迭代器** 定义 multiset<int>::iterator  p; p是迭代器类似于指针可用于指向multiset中的元素

迭代器可用于++，--，用!= ,==比较不可比大小 ，不可相加减

st.begin() 是指向st中的头一个元素 返回值类型为  multiset<int>::iteraor 

st.end() 是指向st中的最后一个元素后面的迭代器

st.find()找到了返回地址 未查到返回st.end()

st.lower_bound(p)  从小到大排序前面紧靠13的元素 为[begin(),p) p--为比p小的最大数

未找到返回begin()

st.upper_bound(p)  从小到大排序后面紧靠13的元素 为[begin(),p) p++为比p大的最小数

未找到返回end()

4.set 与 multiset一样但没有重复元素

pair<t1,t2>类型等价于：

struct{t1 first ; t2 second}