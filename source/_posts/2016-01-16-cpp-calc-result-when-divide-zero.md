title: "C++除数是0/0.0时的结果"
date: 2016-01-16 22:26:53
tags: [算法, c++]
categories: 算法
toc: true
---

在《算法竞赛入门经典》书上看到这个问题，于是做了个小试验，结果出乎意料，故记录如下。

<!--more-->

> 注：实验为OSX系统下，使用g++编译器进行。其它编译器未测试。

## 整形除法
除数为0时编译器警告，结果错误且不可预测，多次执行每次结果不同。

代码
```cpp
#include <stdio.h>
#include <math.h>

int main(int argc, char const *argv[])
{
  printf("%d\n", 9/0);
  return 0;
}
```
编译过程中的警告
```
/Users/test/code/algorithms/aoapc-bac2nd/ch1/playground.cpp:6:19: warning: division by zero is undefined [-Wdivision-by-zero]
  printf("%d\n", 9/0);
                  ^~
1 warning generated.
```
结果
```
1451766616
```

## 浮点型除法
- 若被除数为0，则结果为nan
- 若被除数为非0，则结果为inf

```cpp
#include <stdio.h>
#include <math.h>

int main(int argc, char const *argv[])
{
  printf("%f\n", 1.0/0.0);     // inf
  printf("%f\n", 0.0/0.0);     // nan
  // 若除号两边任意一个为浮点数，则计算时int将被隐式转化为浮点数进行计算，所以如下两例同上面两个例子
  printf("%f\n", 1.0/0);       // inf
  printf("%f\n", 0/0.0);       // nan
  return 0;
}
```
