## 查看当前日期和时间

```go
now := time.Now()
fmt.Printf("now = %v type = %T \n", now, now) //now = 2020-12-09 10:42:28.6242654 +0800 CST m=+0.002992001 type = time.Time 
```

 

## 格式化日期和时间

-   ##### 方式一

    ```go
    fmt.Sprintf("当前年月日 %d-%d-%d %d-%d-%d", now.Year(), now.Month(), now.Day(), now.Hour(), now.Minute(), now.Second())
    ```

-   ##### 方式二

    ```go
    now.Format("2006/01/02 15:04:05") //格式可以变，数字不能变
    ```



## 时间常量

>   在程序中可用于获取指定的单位时间，比如说100毫秒 -> 100 * time.Millisecond

```go
const (
    Nanosecond Duration = 1
    Microsecond     	= 1000 * Nanosecond
    Millisecond     	= 1000 * Microsecond
    Second        		= 1000 * Millisecond
    Minute        		= 60 * Second
    Hour         		= 60 * Minute
)
```



## 常用函数

| **Sleep**    | **使程序休眠一段时间**           |
| ------------ | -------------------------------- |
| **Unix**     | **获取当前时间戳，以秒为单位**   |
| **UnixNano** | **获取当前时间戳，以纳秒为单位** |
|              |                                  |

 


​               

