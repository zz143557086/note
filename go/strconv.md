1. **`strconv.Atoi`**: 用于将字符串转换为整数。

   ```
   func Atoi(s string) (int, error)
   ```

2. **`strconv.Itoa`**: 用于将整数转换为字符串。

   ```
   func Itoa(i int) string
   ```

3. **`strconv.ParseBool`**: 用于将字符串转换为布尔值。

   ```
   func ParseBool(str string) (bool, error)
   ```

4. **`strconv.FormatBool`**: 用于将布尔值转换为字符串。

   ```
   func FormatBool(b bool) string
   ```

5. **`strconv.ParseFloat`**: 用于将字符串转换为浮点数。

   ```
   func ParseFloat(s string, bitSize int) (float64, error)
   ```

6. **`strconv.FormatFloat`**: 用于将浮点数转换为字符串。

   ```
   func FormatFloat(f float64, fmt byte, prec, bitSize int) string
   ```

7. **`strconv.ParseInt`**: 用于将字符串转换为有符号整数。

   ```
   func ParseInt(s string, base int, bitSize int) (int64, error)
   ```

8. **`strconv.ParseUint`**: 用于将字符串转换为无符号整数。

   ```
   func ParseUint(s string, base int, bitSize int) (uint64, error)
   ```

9. **`strconv.FormatInt`**: 用于将有符号整数转换为字符串。

   ```
   func FormatInt(i int64, base int) string
   ```

10. **`strconv.FormatUint`**: 用于将无符号整数转换为字符串。

    ```
    func FormatUint(i uint64, base int) string
    ```

11. **`strconv.Quote`**: 用于在字符串周围添加引号，通常用于转义字符串以保留其特殊字符。

    ```
    func Quote(s string) string
    ```

12. **`strconv.Unquote`**: 用于删除由 `Quote` 添加的引号，并还原字符串的原始值。

    ```
    func Unquote(s string) (string, error)
    ```