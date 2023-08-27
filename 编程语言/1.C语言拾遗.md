# C语言拾遗
* C99标准文档：https://www.open-std.org/jtc1/sc22/wg14/www/docs/n2346.pdf

## 1. 6种行为存在代码可移植性问题
* 由实现定义的行为（implementation-defined behavior）
* 未指定行为（unspecified behavior）
* 未定义行为（undefined behavior）
* 特定区域设置行为（locale-specific behavior）
* 通用扩展（common extensions）

### 1.1 由实现定义行为
#### 1.1.1 定义
* C语言标准未指定的程序行为
* 不同C语言标准的实现可能存在差异
* 但单一实现具有一致性且有案可查的行为

#### 1.1.2 例子
* 字节中的位数

### 1.2 未指定行为（给出多种实现，未指定哪一种实现）
#### 1.2.1 定义
* C语言提供多种选项的程序行为
* 标准不强制实现某种选项

#### 1.2.2 例子
##### （1）子表达式的求值顺序以及副作用发生的顺序
* 下面代码未指定右边表达式从左到右计算还是从右到左计算


```c
// C program to illustrate Unspecified
// Behaviour
#include <stdio.h>

// Declaring x as a global variable
// defining fun1
int x;

// Defining function fun1()
int fun1()
{
	x = 5;
	return 2;
}

// Defining function fun2()
int fun2()
{
	x = 10;
	return 3;
}

// Driver Code
int main()
{
	// Function call
	int sum = fun1() + fun2();

	// Printing the value of x
	printf("%d", x);
	return 0;
}

```

### 1.3 未定义行为（没有定义的行为，同样一种实现也没给）