### defer：用于延迟指定的函数，只能出现在函数的内部

>   -   当go执行到一个defer语句时，不会立即执行该语句，而是将该语句压入到一个栈中（此时也会将相关的值拷贝入栈），继续执行下一个语句
>   -   当函数执行到return语句时，再从栈顶依次取出之前压入的语句执行，执行完以后，函数返回                  

```go
func add(n *int) {
    *n = *n + 1
    fmt.Println("add")
}

func sum(n1 *int, n2 *int) int {
    defer add(n1)             			//丢入栈中延迟执行
    defer add(n2)             			//丢入栈中延迟执行
    fmt.Printf("sum n1 = %d\n", *n1)
    fmt.Printf("sum n2 = %d\n", *n2)
    return *n1 + *n2           			//当函数执行完毕，此时从栈顶开始取出延迟执行的代码，进行执行
}

func main() {
    n1 := 1
    n2 := 2
    s := sum(&n1, &n2)
    fmt.Println(s)
    fmt.Printf("main n1 = %d\n", n1)
    fmt.Printf("main n2 = %d\n", n2)
}
```

 

### 与recover函数配合使用来捕获和处理异常

```go
func test() {
    defer func() {        
        if err := recover(); err != nil {  //recover捕捉到错误，让程序继续执行
            fmt.Println("err = ", err)
        }
    }()

    num1 := 10
    num2 := 0
    result := num1 / num2          			//这里会报错
    fmt.Println("result = ", result)
}

func main() {
    test()
    fmt.Println("hello world")
}
```

