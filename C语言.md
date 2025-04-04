# 06.数组
## 1.数组的概念与定义
>数组是一种数据结构,用于存储一组**相同类型**的数据
数组中的元素在内存中是**连续**存放的
数组通过**下标**来访问元素,下标从0开始
```c
//下标从0开始
int arr[5] = {1,2,3,4,5};
```

## 2.数组的声明与初始化
>数组的声明
- 数组声明格式:**数组类型** **数组名** [**数组的大小**]
- 数组的大小必须是一个**正整数**
- 数组的大小不能为负数,且数组一旦声明了大小,**大小就不能改变**

```c
int a[10];  //合法,最常见的数组声明
int a[3+3];  //合法,3+3的结果是一个正确的正整数
#define X 10  int a[X];  //合法,X是一个符号常量
int n = 10, a[n]; //不合法,n是一个变量
```

>数组的初始化
- 全部初始化:
  ```c
  int arr[5] = {1,2,3,4,5};
- 部分初始化:
  ```c
  int arr[5] = {1,2};  //其余元素为0
- 没有初始化时,数组的默认值(通常为未定义)
```c 
int a[5] = {1,2,3,4,5};  //合法,完全初始化
int a[5] = {1,2,3};  //合法,部分初始化
int a[] = {1,2,3,4,5,6};  //合法,数组的大小由初始化元素个数决定
int a[5] = {1,2,3,4,5);  //不合法,初始化后面的括号应该是花括号
int a[5] = {1,2,3,4,5,6};  //不合法,初始化的元素个数大于数组本身大小
```

## **期末真题** 
>以下能对一堆数组a进行初始化的语句时:
```c
A、int a [5]=(0,1,2,3,4,);  //花括号
B、int a (5)={};  //中括号
C、int a [3]={0,1,2};
D、int a {5}={10*1};  //中括号
```
>在 C 语言中对一维整型数组的正确定义为 ( ) 。
```c
A、int a(10);  //中括号
B、int n=10,a[n];  //一定要是常量,而n是变量
C、int n;a[n];  //同上
D、#define N 10
   int a[N];
```

## 3.数组元素的访问
- 使用下标访问数组中的元素：array **[下标]**
- 下标是从**0**开始，并且下标是一个**整数**
- 下标越界将导致未定义行为
## 期末真题
>1.已知：int a[10]; 则对 a 数组元素的正确引用是:
```c
A、a[10] //下标最大为9
B、a[3.5]  //下标为整数
C、a(5)  //中括号
D、a[0]  
```

>2.若有以下数组说明，则 i=10;a [a [i]] 元素数值是：
```c
int a[12]={1,4,7,10,2,5,8,11,3,6,9,12};
A、10
B、9
C、6  //
D、5
```

## 4.二维数组
>- 二维数组可以看作是 “数组的数组”，即一个包含多个一维数组的数组。
>- 它用来表示矩阵或表格等二维数据。
>- 二维数组的声明格式：**数据类型** **数组名** **[行数][列数]**;
>- 二维数组的**初始化**
int arr[2][3] = {{1,2,3},{4,5,6}};  //合法，第一行的元素是 1，2，3，第二行的元素是 4，5，6
int arr[2][3] = {1,2,3,4,5,6};  //合法，第一行的元素是 1，2，3，第二行的元素是 4，5，6
int arr[2][3] = {1,2,3,4};  //合法，第一行的元素是 1，2，3，第二行的元素是 4，0，0
int arr[][3] = {1,2,3,4};  //合法，行数可以根据初始化元素个数推断出来
int arr[2][] = {1,2,3,4,5};  //不合法，**列数必须指定**

### 期末真题
>求一维数组a[10]中各元素的平均值，打印平均值，并输出小于平均值的元素
假定数组内容为:1.2  7  5  1.8  1.6  0.8  4  1.0  6  2.2
### 答案
```c
#include<stdio.h>

int main()
{
    float a[10] = {1.2,7,5,1.8,1.6,0.8,4,1.0,6,2.2}
    float sum = 0.0;
    float avg = 0.0;
    for(int i = 0; i < 10; i ++)
    {
        sum += a[i];
    }
    avg = sum / 10;
    for(int i = 0; i < 0; i++)
    {
        if a[i] < avg;
        prinf("%f\n",a[i]);
    }
}
```