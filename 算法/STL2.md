#include<map>

1.multimap 里面的元素都是pair形式的

multimap<T1,T2> mp; mp里的元素为

struct{T1 first； 关键字

T2 second； 值 

}

multimap中的元素按照first排序，并可以按first进行查找

缺省的排序规则是"a.first<b.first" 为turn，则a排在b前面

1.make_*pair 生成一个pair<int,StudentInfo>变量

2.typedef multimap<int ,StudentInfo> MAP_STD

typedef 的作用是使 MAP_STD 等价于 multimap<int ,StudentInfo>

