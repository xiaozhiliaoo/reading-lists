# Go语言趣学指南

# 进度

完成



代码仓库：https://github.com/xiaozhiliaoo/go-practice/tree/master/get-programming-with-go

# 笔记

1. 大数：big。无类型常量：存储非常大的值，被用作函数参数的时候，必须转换为有类型变量

2. 字符串不可变，使用UTF-8可变长度编码，每个字符占1～4字节内存。字符串转换可用strconv包。

3. 方法是和特定类型关联的函数，关联的类型是方法名的接收者来指定。

4. 函数作为一等值便于代码拆分和复用，想要动态创建函数，使用带闭包特性的匿名函数。

5. array作为传参会被复制，slice和map不会被复制。

6. Go 通过结构实现组合，并通过名为**结构嵌入**的特殊语言特性实现**方法转发**。

7. 使用继承相比，使用组合构建的软件通常更灵活、复用程度更高并且更容易修改。

8. Go 语言通过组合**结构和方法**，在没有引入任何新特性的情况下实现了传统语言的面向对象特性。构造函数是普通函数，不是特殊的语言特性。

9. 对传统继承的使用并不是必需的；所有使用继承解决的问题都可以通过其他方法解决。

10. 写入接口Writer，可以将任意内容写入任何地方。

11. 类型关心自己存储了什么值，但是接口关心可以做什么而不是存储了什么值。类型通过方法表达自己的行为，而接口则通过列举类型必须满足的一组方法来进行声明。

12. 同时使用组合和接口将构成非常强大的设计工具。

13. fmt 包声明Stringer接口，一种类型只要提供了String 方法，它的值就能够为Println、Sprintf 等打印函数所用。

14. Go 通过简单的、通常只有单个方法的接口，来鼓励组合而不是继承，这些接口在各个组件之间形成了简明易懂的界限。 - Rob Pike

15. 地址操作符 & 解引用 * ，指针类型 * int 。指针存储的是内存地址。

16. 星号放在类型前面：声明指针类型，星号放在变量前面：解引用变量指向的值。

17. 在访问字段时对结构体进行解引用并不是必需的。

18. 地址操作符可以合法地放置在变量和复合字面量前面，但不能放置在字符串字面量或整数字面量前面。

19. go会对指向结构体，数组指针进行自动解引用，但不对slice和map自动解引用。

20. 映射在被赋值或者被作为实参传递的时候不会被复制。因为映射实际上就是一种隐式指针。

21. 隐式指针：1 映射也是指针 2 切片指向数组

22. Go 语言的函数和方法都以传值方式传递形参，这意味着函数总是基于被传递实参的副本进行操作。当指针被传递至函数时，函数将接收到传入内存地址的副本，在此之后，函数就可以通过解引用内存地址来修改指针指向的值。

23. 使用指针作为接收者的策略应该是始终如一的。如果一种类型的某些方法需要用到指针作为接收者，就应该为这种类型的所有方法都使用指针作为接收者。

24. 实现修改：将指针作为形参，将指针作为接受者。

25. nil函数值，nil切片（vs 空切片），nil映射，nil接口

26. slice的零值是nil，代表没有对应的底层数组，map的零值是nil，代表没有引用任何hash表。结构体的零值是结构体成员的零值。指针的零值为nil。

27. 在发生错误时，调用返回的其他值可能会被设置成相应类型的零值，但也可能会包含不完整的数据或者完全不同的其他内容。总体来说，每当有错误发生时，同一调用返回的其他值通常就不再值得信任。

28. Go 语言鼓励使用者思考并处理函数可能返回的所有错误。

29. 减少错误处理代码的一种策略是，将程序中不会出错的部分和那些包含潜在出错隐患的部分隔离开来。

30. 因为错误也是值，所以Go 编程语言提供的所有功能都可以用于处理它们。

31. Go 程序将使用带有Err 前缀的变量来存储错误消息。

32. 类型断言：值从接口类型重新转换成底层的具体类型。err.(SudokuError)  error类型转换成SudokuError。

33. Go 语言的错误值机制促使开发者考虑错误，而不是像处理异常那样默认将其忽略，这有助于生成更为可靠的软件。除此之外，因为错误值机制不需要用到特殊关键字，所以它比异常简单而灵活。

34. 如果某个被defer的函数调用了recover，那么panic将会停止，而程序则会继续运行。这种恢复机制类似于其他语言中的catch、except 和rescue。

35. Go处理错误通过error，没有异常机制。Java处理错误是通过异常机制。

36. 并发任务之间则通过相互通信来达成共同的目的。

37. 单个通道（都产生相同类型的值）来等待多个goroutine，select处理多个通道。

38. 被阻塞的goroutine 并不消耗任何资源。goroutine 会静静地停在那里，等待导致它阻塞的事情发生，然后解除阻塞。

39. “从通道里面读取值，直到它被关闭为止”，所以Go通过在range 语句里面使用通道，程序可以在通道被关闭之前，一直从通道里面读取值。

40. range 语句可以从通道中读取所有值，直到通道关闭为止。

41. 互斥锁并未内置在Go 语言当中，而是通过sync 包提供，而通道是内置的。

42. 将sync.Mutex 用作结构成员的做法是一种常见的模式。

43. 为了保证互斥锁的使用安全，遵守以下规则：尽可能地简化互斥锁保护的代码，对每一份共享状态只使用一个互斥锁。

44. 长时间运行的工作进程：

    `func worker() { for { 	select { 		// 在此处等待通道 	} } }`

    

45. 通道常常被看作是实现细节，所以一般都会把通道隐藏在方法的后面。

46. 通道可以发送任何类型的值。





# 参考
