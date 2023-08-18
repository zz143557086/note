1. strchr(a,b)  返回null表面b字符没在字符串a中

   返回 ture表面b字符在字符串a中

2. strlen(a) a字符串长度 

3. strcat（a，b） b拼接到a后面保存为a

4. strncat 

   ```c++
   /* 部分连接（这里将str2前6个字符与str1连接）
   strncat (str1, str2, 6);
   连接
   string a="ads",b="djak";
   a+b//拼接
   ```

5. strupr(a)  字符串a变为大写

6. strlwr（a）字符串a变为小写

7. strcmp 比较字符串

8. eg strcmp（"qqq","qq1"）相同返回0 前者小于后这返回<0

9. strcpy（a,"ss"）将后面的字符串拷贝到前面的变量

10. strncpy
    strncpy与strcpy很类似，只是可以指定复制多少个字符。它的原型是：

    ```c++
    /* 部分复制(这里是复制5个字符): */
        strncpy ( str3, str2, 5 );
    ```

11. memset(a,'\0'.sizeof(a)); 将字符串a元素清0

    ```c++
    /*ptr指向要修改的内存块的起始地址，value是要修改成什么值，num是修改多少个。*/
    void * memset ( void * ptr, int value, size_t num );
    ```

    

12. `strchr`函数可以在一个字符数组里找某个字符第一次出现的位置

    ```c++
    /*显然前一个是原字符数组，后一个是要查找的字符。*/
     pch = strchr(str, 's'); //返回从s开始后str所有字符
             cout<<s-str +1;//返回s第一次出现在str的位置
    ```

13. strstr可以在一个字符数组里查找另一个字符数组第一次出现的位置。

    ```c++
    pch = strstr (str1, str2); 返回从str2算起后str1所有字符
        cout<<str2-str1+1//返回str2第一次出现在str1的位置
    ```

14. empty(str) // 判断字符串是否为空 为空返回1 不为空返回0
