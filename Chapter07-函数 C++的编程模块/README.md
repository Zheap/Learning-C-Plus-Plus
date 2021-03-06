# 第7章 函数---C++的编程模块

## 1. 函数是如何返回值的？

通常，函数将返回值复制到指定的CPU寄存器或内存单元中来将其返回。随后，调用程序将查看该内存单元。

返回程序和调用函数必须就该内存单元中存储的数据的类型达成一致。

函数原型将返回值类型告知调用程序，而函数定义命令被调用函数应返回什么类型的数据。

```c++
...
double cube(double x);     // function prototype 函数原型
...
int main()
{
    ...
    double q = cube(1.2);  // function call      函数调用
    ...
}

double cube(double x)      // function definition 函数定义
{
    return x*x;
}
```

### 1.1 函数原型

**函数原型其实可以理解成就是在头文件中的函数声明**

#### 1.1.1 为什么需要函数原型？

函数原型描述了函数到编译器的接口，也就是说，它将函数返回值的类型（如果有的话）以及参数的类型和数量告诉编译器。

避免使用函数原型的唯一方法就是在函数被调用之前就定义好。

#### 1.1.2 函数原型不要求提供变量名，有类型列表就可以了

即 void  cheers(int); 也是可以的，<u>*注意这里是函数原型，不是函数定义*</u>

**通常，在函数原型的参数列表中，可以包含变量名，也可以不包含。原型中的变量名相当于是占位符，因此不必与函数定义中的变量名相同。**

