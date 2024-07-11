# 命名规则
建议是**驼峰命名**
**字母或下划线开头，可以是任意数量的字母、数字、下划线**
**大小写字母敏感**
命名不能使用关键字
```
break      default       func     interface   select
case       defer         go       map         struct
chan       else          goto     package     switch
const      fallthrough   if       range       type
continue   for           import   return      var

内建常量: true false iota nil

内建类型: int int8 int16 int32 int64
          uint uint8 uint16 uint32 uint64 uintptr
          float32 float64 complex128 complex64
          bool byte rune string error

内建函数: make len cap new append copy close delete
          complex real imag
          panic recover
```

局部变量建议使用短小的名字。
如果变量是全局变量或者生命周期很长，建议用含义准确的单词命名

# 声明变量
``` Go
// 定义变量
var 变量名字 类型 = 表达式
var a int = 1
可以省略掉类型 int，系统会自动推断变量a的类型
var a = 123
可以省略掉表达式，此时a的默认值是0
var a int
1. 数值类型变量对应的零值是0
2. 布尔类型变量对应的零值是false
3. 字符串类型对应的零值是空字符串
4. 接口或引用类型（包括slice、指针、map、chan和函数）变量对应的零值是nil
5. 数组或结构体等聚合类型对应的零值是每个元素或字段都是对应该类型的零值。
// 定义常量
const c = 111
```
// 定义类型


// 定义函数实体

学习文档[Go语言圣经](https://gopl-zh.github.io/ch2/ch2.html)