#### 防止sql注入

再sql语句中先使用占位符代表数据

最后通过Exec将实际值填充到占位符中

```
stmt, err := mydb.DBConn().Prepare(
    "insert ignore into tbl_user (`user_name`,`user_pwd`) values (?,?)")
if err != nil {
    // 处理错误
}

// 将实际值填充到占位符中
user := "username"
password := "password"
_, err = stmt.Exec(user, password)
if err != nil {
    // 处理错误
}
```

