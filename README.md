# Embedded-Learning
Self-learning Embedded Knowledge (Beginner Edition)

Based on the following repositories.
[GitHub - m3y54m/Embedded-Engineering-Roadmap](https://github.com/m3y54m/Embedded-Engineering-Roadmap "https://github.com/m3y54m/Embedded-Engineering-Roadmap")

# Catalog
- [Programming Fundamentals](#programming-fundamentals)
- [Programming Languages](#programming-languages)
- [Operating Systems](#operating-systems)
- [Microcontrollers](#microcontrollers)
- [Interfaces & Protocols](#interfaces--protocols)

## Programming Fundamentals
(Related contents)
- [Algorithms & Data Structures](#algorithms--data-structures)
- [Design Patterns](#design-patterns)
- [State Machines](#state-machines)
- [Memory Management](#memory-management)

### Algorithms & Data Structures
学习书籍《[Hello 算法](https://www.hello-algo.com/ "https://www.hello-algo.com/")》

1. [初始算法](#1-初始算法)
2. [复杂度分析](#2-复杂度分析)
3. [数据结构](#3-数据结构)
4. [数组与链表](#4-数组与链表)
5. [栈和队列](#5-栈和队列)
6. [哈希表](#6-哈希表)
7. [树](#7-树)
8. [堆](#8-堆)
9. [图](#9-图)
10. [搜索](#10-搜索)
11. [排序](#11-排序)
12. [分治](#12-分治)
13. [回溯](#13-回溯)
14. [动态规划](#14-动态规划)
15. [贪心](#15-贪心)

#### 1. 初始算法

**算法**（algorithm）是在有限时间内解决特定问题的一组指令或操作步骤。

> 问题是明确的，包含清晰的输入和输出定义。
> 具有可行性，能够在有限步骤、时间和内存空间下完成。
> 各步骤都有确定的含义，在相同的输入和运行条件下，输出始终相同。

**数据结构**（data structure）是组织和存储数据的方式，涵盖数据内容、数据之间关系和数据操作方法。

> 空间占用尽量少，以节省计算机内存。
> 数据操作尽可能快速，涵盖数据访问、添加、删除、更新等。
> 提供简洁的数据表示和逻辑信息，以便算法高效运行。

#### 2. 复杂度分析

渐近复杂度分析（asymptotic complexity analysis），简称**复杂度分析**。
它描述了随着输入数据大小的增加，算法执行所需时间和空间的增长**趋势**。

**时间复杂度**（time complexity）：用于衡量算法运行时间随数据量增长的趋势。
> $O(1) < O(\log n) < O(n) < O(n \log n) < O(n^2) < O(2^n) < O(n!)$  
> 常数阶 &lt; 对数阶 &lt; 线性阶 &lt; 线性对数阶 &lt; 平方阶 &lt; 指数阶 &lt; 阶乘阶

**空间复杂度**（space complexity）用于衡量算法占用内存空间随数据量增长的趋势。
> $O(1) < O(\log n) < O(n) < O(n \log n) < O(n^2) < O(2^n)$  
> 常数阶 &lt; 对数阶 &lt; 线性阶 &lt; 平方阶 &lt; 指数阶  
> **通常只关注最差空间复杂度**

#### 3. 数据结构

- ##### 数据结构分类
逻辑结构：**线性**和**非线性**。
> 线性数据结构：**数组**、**链表**、**栈**、**队列**、**哈希表**，元素之间是**一对一**的顺序关系。
> 非线性数据结构：树、堆、图、哈希表。
> 
> 非线性数据结构可以进一步划分为**树形结构**和**网状结构**。
>> 树形结构：**树、堆、哈希表**，元素之间是**一对多**的关系。
>> 网状结构：**图**，元素之间是**多对多**的关系。

物理结构：连续与分散。

- ##### 基本数据类型

> 一个二进制位即为 1 比特。
> 1 字节（byte）由 8 比特（bit）组成。

基本数据类型是 CPU 可以直接进行运算的类型，以二进制的形式存储在计算机中。

|类型|||
|-|-|-|
|整数类型| `byte`、`short`、`int`、`long`| |
|浮点数类型| `float`、`double`| 表示小数|
|字符类型| `char`| 表示字母、标点符号、表情符号|
|布尔类型| `bool`| 表示“是”与“否”判断|

- ##### 原码、反码和补码

  数字是以“补码“的形式存储在计算机中的。（补码 $10000000$ 代表 $−128$）

1. 原码（sign-magnitude）：二进制表示的最高位为符号位，其中 $0$ 表正，$1$ 表负，其余位表示数字的值。
2. 反码（1's complement）：正数的反码与其原码相同，负数的反码是对其**原码除符号位外的所有位取反**。（负数的原码不能直接用于运算，因此引入反码）
3. 补码（2's complement）：正数的补码与其原码相同，负数的补码是在其**反码的基础上加 1** 。（数字零的原码有 $+0$ 和 $−0$ 两种表示方式，与原码一样，反码也存在正负零歧义问题，因此引入了补码）

#### 4. 数组与链表

- ##### 数组
数组（array）是一种线性数据结构，其**将相同类型的元素存储在连续的内存空间**中。我们将元素在数组中的位置称为该元素的索引（index）。

初始化，访问元素，插入元素，删除元素，遍历数组，查找元素，扩容数组
```c
/* 初始化数组 */
int arr[5] = { 0 }; // { 0, 0, 0, 0, 0 }
int nums[5] = { 1, 3, 2, 5, 4 };
```
```c
/* 随机访问元素 */
int randomAccess(int *nums, int size) {
    // 在区间 [0, size) 中随机抽取一个数字
    int randomIndex = rand() % size;
    // 获取并返回随机元素
    int randomNum = nums[randomIndex];
    return randomNum;
}
```

- ##### 链表
链表（linked list）是一种线性数据结构，其中的每个元素都是一个节点对象，各个节点通过“引用”相连接。引用记录了下一个节点的内存地址，通过它可以从当前节点访问到下一个节点。

链表的组成单位是节点（node）对象。每个节点都包含两项数据：节点的“值”和指向下一节点的“引用”。

初始化链表，插入节点，删除节点，访问节点，查找节点
```c
/* 链表节点结构体 */
typedef struct ListNode {
    int val;               // 节点值
    struct ListNode *next; // 指向下一节点的指针
} ListNode;

/* 构造函数 */
ListNode *newListNode(int val) {
    ListNode *node;
    node = (ListNode *) malloc(sizeof(ListNode));
    node->val = val;
    node->next = NULL;
    return node;
}
```

#### 5. 栈和队列

- ##### 栈

```c
栈（stack）是一种遵循先入后出逻辑的线性数据结构。
/* 基于链表实现的栈 */
typedef struct {
    ListNode *top; // 将头节点作为栈顶
    int size;      // 栈的长度
} LinkedListStack;

/* 构造函数 */
LinkedListStack *newLinkedListStack() {
    LinkedListStack *s = malloc(sizeof(LinkedListStack));
    s->top = NULL;
    s->size = 0;
    return s;
}
```

- ##### 队列

#### 6. 哈希表

#### 7. 树

#### 8. 堆

#### 9. 图
#### 10. 搜索
#### 11. 排序
#### 12. 分治
#### 13. 回溯
#### 14. 动态规划
#### 15. 贪心

(Related contents)
### Design Patterns
(Related contents)
### State Machines
(Related contents)
### Memory Management
(Related contents)

## Programming Languages
- [C](#c)  
- [C++](#c-1)  
- [Python](#python)
  
### C
学习书籍《C和指针》（Pointers On C）

1. [快速上手](#1-快速上手)
2. [基本概念](#2-基本概念)
3. [数据](#3-数据)
4. [语句](#4-语句)
5. [操作符和表达式](#5-操作符和表达式)
6. [指针](#6-指针)
7. [函数](#7-函数)
8. [数组](#8-数组)
9. [字符串、字符和字节](#9-字符串字符和字节)
10. [结构和联合](#10-结构和联合)
11. [动态内存分配](#11-动态内存分配)
12. [使用结构和指针](#12-使用结构和指针)
13. [高级指针话题](#13-高级指针话题)
14. [预处理器](#14-预处理器)
15. [输入/输出函数](#15-输入输出函数)
16. [标准函数库](#16-标准函数库)
17. [经典抽象数据类型](#17-经典抽象数据类型)
18. [运行时环境](#18-运行时环境)

#### 1. 快速上手

- ##### 空白和注释

注释（comment），注释以符号`/*`开始，以符号`*/`结束，注释不能嵌套。
```c
/* 注释1 */
  
/* 
** 注释2
*/
 
// 注释3
```

逻辑上删除一段代码，使用`#if`指令。（详见预处理器的条件编译）
```c
#if 0
    statements
#endif 
```

- ##### 预处理指令

```c
#include <stdio.h>
#define MAX_COL 20
```
预处理器用名叫`stdio.h`的库函数头文件的内容**替换**第一条`#include`指令语句。
另外一条预处理指令`#define`，将名字`MAX_COl`定义为`20`。
`MAX_COl`为字面值常量，**一般都大写**，在源代码中会被替换为定义的值。

```c
int read_column_num( int cols[], int max );
void rearrange( char *output, char const *input,
        int n_cols, int const cols[]);
```
这些声明被成为函数原型（function prototype）。
其中的参数名字不是必须的，参数名的目的是提示它们的作用。

`rearrange`函数接收4个参数，第1个和第2个参数为指针（pointer）。

关键字`void`表示函数不返回任何值，无返回值的函数被称为过程（procedure）。



- ##### main函数
`main`函数，程序的起点
**其他......**

#### 2. 基本概念

组成一个程序的每个（或多个）源代码通过编译过程分别转换为目标代码（object code）。

然后各个目标文件由链接器（linker）捆绑在一起，形成单一可执行程序。

源代码 编译 &rarr; 目标代码 与函数库 链接 &rarr; 可执行文件

**预处理器**（preprocessor） &rarr; **解析**（parse）&rarr; **优化器**（optimizer）
预处理器 &rarr; 执行文本操作，替换
解析 &rarr; 产生绝大多数错误和警告
优化 &rarr; 处理目标代码，使它效率更高

编译链接

**其他......**

#### 3. 数据

- ##### 基本数据类型

1. 整型：字符，短整型，整型，长整型。都分有符号（singed）和无符号（unsigned）。
    长整型至少应该和整型一样长，而整型至少应该和短整型一样长。

2. 字面值（literal）等价字面值常量，不允许发生改变。命名常量是声明为`const`的变量。
  在整型字面值后面添加字符`L`和`l`，可以使这个整数被解释为`long`整型值。
  字符`U`或`u`则用于把数值指定为`unsigned`整型值。`UL`则为`unsigned long`整型值。

3. 字符常量：`'R'`，宽字符常量（wide character literal）：`L'R'`。

4. 枚举（enumerated）类型就是指它的值为符号常量而不是字面值类型。
  默认`CPU`是`0`，`PINT`是`1`，以此类推，未指定则它的值比前一个符号名的值大1。
```c
/* 声明一个类型，称为Jar_Type */
enum Jar_Type { CPU, PINT, QUART, HALF_GALLON, GALLON };  //类型名为Jar_Type
/* 声明这种类型的变量 */
enum Jar_Type milk_jug, gas_can, medicine_bottle;
/* 一步到位 */
enum { CPU, PINT, QUART, HALF_GALLON, GALLON }
    milk_jug, gas_can, medicine_bottle;
/* 初始化 */
enum Jar_Type { CPU = 8, PINT = 16, QUART = 32,
        HALF_GALLON = 64, GALLON = 128 }; 
```

5. 浮点数包括`float`、`double`、`long double`类型。
  浮点数字面值缺省的情况下都为double类型。后跟`L`或`l`，则表示为`long double`类型。后跟`F` 或`f`，则表示`float`类型。

6. 指针
  变量的值存储在计算机的内存中，每个变量都占据内存的一个特定的位置。每个内存位置都由地址唯一确定并引用。指针只是地址的另外一个名字，指针变量就是一个其值为另外一个（一些）内存地址的变量。

- ##### 基本声明

1. `typedef`：为各种数据类型定义新名字。
```c
/* 声明一个指向char型数据的指针，指针名为ptr_to_char */
char *ptr_to_char;
/* 为 char * 类型，定义新名字为ptr_to_char */
typedef char * ptr_to_char;
/* 声明一个ptr_to_char类型的变量a */
ptr_to_char a;
```
2. 常量
```c
/* 一个指向整型常量的指针 */
int const *ptr;  //可以修改指针的值，不能修改它所指向的值
/* 一个指向整型的常量指针 */
int * const ptr;  //指针是常量，它的值无法修改，但可以修改它所指向的值
/* 创建名字常量 */
#define MAX_SIZE 50
/*
** int const a;  等价于  const int a;
*/
```

- ##### 作用域
  作用域是指变量、函数或对象在程序中可以被访问的范围。

1. 文件作用域
2. 函数作用域
3. 代码块作用域
4. 原型作用域
  
- ##### 链接属性
  链接属性描述了在程序的不同部分（例如不同的源文件）中，标识符（如变量或函数）如何关联和共享的特性。

1. external（外部链接）
不论声明多少次，位于几个源文件都表示同一个实体。

2. internal（内部链接）
在同一个源文件内的所有声明中都指向同一个实体，但位于不同源文件的多个声明则分属不同的实体。

3. none（无链接）
总是被当作单独的个体，多个声明被当作不同的独立实体。
```c
/* 被源文件私有 */
static int b;
/* 函数声明为static，防止它被其他源文件调用 */
static int c( int d ){}
```
全局变量和未使用`static`关键字修饰的函数默认具有外部链接属性，可被其他文件通过`extern`关键字引用。

> `extern`关键字只能用于源文件的标识符的第 1 次声明，后续声明不改变其链接属性。
> `static`关键字只对缺省链接属性为 external 的声明才有改变链接属性的效果。

- ##### 存储类型

1. 静态变量（`static`）：代码块之外声明的变量，存储在静态内存中，在整个程序执行过程中一直存在，不允许从其他文件访问。
2. 自动变量（`auto`）：代码块内部声明的变量，缺省存储类型为`auto`，存储在堆栈中，作用域整个代码块（声明为`static`变量后，不存储于堆栈中，值在程序整个执行期一直保持，存储类型从自动变为静态）。
> 关键字`register`可以用于自动变量的声明，存储于机器的硬件寄存器，**寄存器变量**。
> 形式参数，声明在函数头部，存于堆栈中，作用域整个函数，不允许声明为`static`。

> `static`关键字
> 用于函数定义，或代码块之外的变量声明，`static`只改变链接属性。
> 用于代码块内的变量声明，只改变存储类型，不改变链接属性和作用域。

#### 4. 语句
C最简单的空语句 `;` 。

表达式语句 = 表达式 + `;` 。

- `if`语句
  
  `else`子句从属于最靠近它的不完整的`if`语句。
```c
if ( expression )
    statement
else
    statement
```
C并不具备布尔类型，用整型替代（零值表“假”，非零值表“真”）。

- `while`语句

```c
while ( expression )
    statement
```
`break`语句，用于永久终止循环。
`continue`语句，永久终止当前的那次循环。
`break`语句、`continue`语句，只对最内层的循环起作用，不影响外侧循环的执行。

- `for`语句
  `statement`循环体，`expression1`初始化，`expression2`条件，`expression3`调整。
```c
for ( expression1; expression2; expression3 )
    statement
```
在`for`语句中，`break`语句立即退出循环，`contiue`语句把控制流直接转移到调整部分。

- `do`语句
```c
do
    statement
while ( expression );
```
当循环体至少执行一次时，选择`do`。

- `switch`语句

  `expression`的结果必须是整型值。
```c
switch ( expression )
    statement
```
以下为常用写法
```c
switch ( expression ) {
case constant-expression1:
      statement
      break;
case constant-expression2:
      statement
      break;
default:
      statement
}
```
- `goto`语句

  不建议使用
```c
goto ABC;  // 会跳转到语句标签ABC处，然后执行statement

ABC:
    statement
```

#### 5. 操作符和表达式

- 算数操作符

  加减乘除：`+` `-` `*` `/`
  取余：`%`

- 移位操作符

  左移：`<<`
  右移：`>>`
  算数移位：左移补 $0$，右移的位由符号位决定，符号位为 $1$ 则移入 $1$，为 $0$ 则移入 $0$。
  逻辑移位：左移、右移时用 $0$ 填充。

- 位操作符

  与（AND）：`&`
  或（OR）：`|`
  异或（XOR）：`^`（同0异1）

- 复合赋值符

  算数操作符，移位操作符，位操作符，与`=`复合。
  应尽量使用复合赋值符。
```c
/* 例如 以下两个表达式的等价 */
a += expression;
a = a + (expression);
```
- 单目操作符

  逻辑取反： `!`
  按位取反：`~`
  取负值：`-`，啥也没干：`+`
  取地址：`&`
  间接访问操作符：`*`，与指针一起使用，访问指针所指向的值
  强制类型转换：`(类型)`
  返操作数的类型长度：`sizeof`，以字节为单位，如果操作数是数组则返回数组长度
  增值操作符：`++` ，后缀的优先级大于前缀
  减值操作符：`--`，后缀的优先级大于前缀
 
> 如果`sizeof`判断表达式的长度时，不需要对表达式进行求值。
> 如果对整个表达式的进行强制类型转换时，必须用括号把整个表达式括起来。

- 关系操作符

  结果为一个整型值，符合为 1，不符合为 0。
   `>` `>=` `<` `<=` `!=` `==`

- 逻辑操作符

  `&&`：`expression1 && expression2`，先对左操作数求值，若为假，则不再求值。
  `||`：同上，称为短路性质。

- 条件操作符

  `expression1 ? expression2 : expression3`：计算 expression1，若为真，整个表达式的值为 expression；若为假，整个表达式的值为 expression3。

- 逗号操作符

  `expression1, expression2, ... , expressionN`：对每个表达式自左向右逐个求值，整个逗号 表达式的值就是最后那个表达式的值。

- ##### 优先级

  优先级由高到低排序。
优先级只对相邻的操作符的执行顺序起作用。
执行顺序，由优先级决定，同优先级看结合性

| 操作符                        | 描述                         | 结合性    |
|-------------------------|-----------------------|------------|
| `()` `[]` `.` `->`             | 括号、下标引用、访问结构成员、访问指针成员 | L-R   |
| `++` `--` `!` `~`  `+` `-` `++` `--` `*` `&` `sizeof` `(类型)`  | **单目**操作符，`++` `--`后缀优先级高于前缀，后缀L-R      | **R-L**   |
| `*` `/` `%`                    | 乘法、除法、取余         | L-R   |
| `+` `-`                         | 加法和减法                    | L-R   |
| `<<` `>>`                   | 移位操作                        | L-R   |
| `>` `>=` `<` `<=`        | 关系操作符                    | L-R   |
| `==` `!=`                    | 相等与不相等                 | L-R   |
| `&`                             | 按位与                           | L-R   |
| `^`                             | 按位异或                        | L-R   |
| `\|`                              | 按位或                           | L-R   |
| `&&`                          | 逻辑与                           | L-R   |
| `\|\|`                           | 逻辑或                           | L-R   |
| `?:`                             | 条件操作符                    | N/A   |
| `=` `+=` `-=` `*=` `/=` `%=` `<<=` `>>=` `&=` `^=` `\|=` | 赋值操作符     | **R-L**   |
| `,`                             | 逗号操作符                         | L-R   |

#### 6. 指针

计算机的内存由数以万计的位（bit）组成。
每个字节（byte）包含8个位。
许多机器以字为单位存储整数，每个字一般有 2 字节（16位）或 4 字节（32位）组成。

硬件事项：边界对齐（boundary alignment）

间接访问（indirection）或解引用指针（dereferencing the pointer）：通过指针访问它所指向的地址的过程。

`NULL`指针，不指向任何东西，可以赋 0 值。对`NULL`指针解引用非法。

变量的值就是分配该变量的内存位置所存储的数值。

不能简单地通过检查一个值的位来判断它的类型。

如果变量是静态的，会被初始化位 0。

```c
int b = 10;
int *a = &b;
// *a = b
// a = &b
```
```c
/* 同上 */
int a = 12;
int *b = &a;
int **c = &b;
```
指针运算
> 算数运算
> 指针 $±$ 整数 $=$ 指针，相当于移位
> 指针 $-$ 指针 $=$ 指针在内存中的距离，以长度为单位
>
> 关系运算
> `<` `<=` `>` `>=` 前提是指向同一个数组中的元素。
> 可以在两个任意的指针间执行相等或不相等测试

标准允许指向数组元素的指针与指向数组最后一个元素后面的那个内存位置的指针进行比较，但不允许与指向数组第 1 个元素之前的那个内存位置的指针进行比较

#### 7. 函数

函数定义
```c
/* 
** 类型
** 函数名( 形式参数 )
** 代码块
*/
function_name()  // 最简单的函数
{
}
```
C函数的所有参数均以“传值调用”方式进行传递，这意味着函数将获得参数值的一份拷贝。
数组如果传递的是数组名，则为“传址调用”。

抽象数据类型（ADT，Abstract Data Type），或称黑盒，由接口和实现组成。

递归函数：直接或间接调用自身地函数。
尾部递归：递归调用是函数执行的最后一项任务。

常见的原型使用方法是把原型放在一个单独文件。

可变参数列表：参数的可变列表位于一个和多个普通参数（命名参数）的后面，在函数原型中以一个省略号表示。

#### 8. 数组

##### 8.1 一维数组

```c
int a[10];
int b[10];
b = a;
// 非法
// 不能使用赋值符把一个数组的所有元素复制到另一个数组。只能使用循环，每次复制一个元素。
```

```c
/* 下标引用 */
int array[10];
int *ap = array + 2;

ap = &array[2];
ap = array + 2;

*ap = array[2] = *(array + 2);

ap + 6 = &array[8] = array + 8;
*ap + 6 = array[2] + 6;
*(ap + 6) = array[8] = *(array + 8) = ap[6];

array[0] = *(array + (0));
ap[0] = *(ap + 0) = *ap; // 也可
ap[-1] = array[1]; // 要防止越界
```
指针比下标更有效率的场合：在数组中固定移动时，指针效率更高。
```c
/* 初始化字符数组*/
char message[] = "Hello";
```

##### 8.2 多维数组

- 下标与指针
```c
int array[3];
int matrix[3][10]; // 矩阵
/* 
** 数组名 matrix 的值是一个指向它第一个元素的指针
** 所以 matrix 是一个指向一个包含10个整型元素的的指针
*/

matrix + 1 = &matrix[1];
*(matrix + 1) = matrix[1];

*(matrix + 1) + 5 = &matrix[1][5];
*(*(matrix + 1) + 5) = matrix[1][5];

int (*p)[10]; // 指向二维整型数组的指针
int (*p)[] = matrix;
```
- 作为函数参数的数组
```c
// 一维数组
void func1( int *vec );
void func1( int vec[] );
int vector[10];
func1(vector);

//二维数组
void func2( int (*mat)[10] );
void func2( int mat[][10] );
int martix[3][10];
func2(matrix);
```
- 初始化
```c
int matrix[2][3] = { 100, 101, 102, 110, 111, 112 };
int matrix[2][3] = {
    {100, 101, 102}, 
    {110, 111, 112}
};
```
在多维数组在，只有第一维才能根据初始化列表缺省地提供。

- 指针数组
```c
int *api[10]; // api是个数组，有10个元素，元素类型为指向整型地指针
```
> 在绝大多数表达式中，数组名的值是指向数组第一个元素的指针
> 1. `sizeof`返回整个数组所占的字节，而不是一个指针所占的字节
> 2. 单目操作符`&`返回一个指向数组的指针

#### 9. 字符串、字符和字节

字符串就是一串零个或多个字符，并且以一个位模式为全 0 的`NUL`字节结尾。
头文件`string.h`包含字符串函数所需的原型和声明。
```c
/* 字符串的长度是其所包含的字符个数 */
size_t strlen( char const *string ); // 库函数 strlen 原型
// size_t 无符号整数类型，在 stddef.h 中定义
```
- 复制字符串
```c
/* 把 src 字符串复制到 dst */
char *strcpy( char *dst, char const *src );
// 若 src 和 dst 在内存中重叠，结果未定义
```
- 连接字符串
```c
/* 把 src 字符串的副本添加到 dst 字符串末尾 */
char *strcat( char *dst, char const *src );
// 若 src 和 dst 的位置发生重叠，结果未定义
```
**复制**字符串和**连接**字符串都返回第一个参数的副本，即一个指向目标字符数组的指针。

- 字符串比较
```c
/* 
** 如果s1小于s2，则函数返回一个小于零的值；
** 如果s1大于s2，则函数返回一个大于零的值；
** 如果s1等于s2，则函数返回零。
*/
int strcmp( char const *s1, char const *s2 ); // 相当于 return s1 - s2
```
- 长度受限的字符串函数
函数接受一个显示的长度参数，用于限定复制或比较的字符串
```c
/*
** 向 dst 写入 len 个字符
** 如果 strlen(src) 的值小于 len，则 dst 数组用额外的 NUL 字节填充到 len 长度
** 如果 strlen(src) 的值大于 len，只复制 len 个字符，且不会自动追加 NUL 字节
*/
char *strncpy( char *dst, char const *src, size_t len );

/*
** 最多向目标数组复制 len 个字符（再加一个结尾的 NUL 字节）
** 不管剩余空间是否够
*/
char *strncat( char *dst, char const *src, size_t len );

/* 最多比较 len 个字节 */
char strncmp( char const *s1, char const *s2, size_t len );
```
- 查找字符串
1. 查找一个字符
   在一个字符串中查找一个特定字符
```c
/*
** strchr 在字符串 str 中查找字符 ch 第一次出现的位置 
** 找到后返回一个指向该位置的指针，未找到返回 NULL 指针
*/
char *strchr( char const *str, int ch ); // 第二个参数为整型值

/* strrchr 功能与 strchr 基本一致，返回的是ch字符最后一次出现的位置 */
char *strrchr( char const *str, int ch );
```
2. ==查找任何几个字符==
   查找任何一组字符第一次在字符串出现的位置
```c
/*
** 
** 
*/
char *strpbrk( char const *str, char const *group );
```
3. 查找一个字串
```c


```
4. 查找一个字符串前缀
```c


```
5. 查找标记
```c


```
- 错误信息
- 字符操作
- 内存操作

#### 10. 结构和联合

1. ##### 结构基础知识

[结构声明](#结构声明)
[结构用法](#结构用法)
[结构成员](#结构成员)
[结构自引用](#结构自引用)
[不完整声明](#不完整声明)
[结构的初始化](#结构的初始化)

2. ##### 结构、指针和成员



聚合数据类型（aggregate data type）：能够同时存储一个以上的单独数据。
C提供两种类型的聚合数据类型：数组和结构。

结构是一些值的集合，这些值称为它的成员（member），但一个结构的各个成员可能具有不同的类型。使用结构可以把不同类型的值存储在一起。

结构变量属于标量类型。

- ##### 结构声明
```c
struct tag {        // 标签tag
    member-list     // 成员：类型+名
} varisble-list;    // 变量名
```
标签不同，相同的成员列表，为截然不同的数据类型，`z = &x;` 是非法的。
```c
struct {
    int a;
    char b;
    float c;
} x; 
/* 声明一个名为 x 的变量，它包含3个成员：a、b、c */

struct {
    int a;
    char b;
    float c;
} y[20], *z;
/*
** 这个声明创建了 y 和 z。
** y是一个数组，它包含20个结构。
** z是一个指针，它指向这个类型的结构
*/

z = &x;
```
- ##### 结构用法
```c
/* 正常用法 */
struct SIMPLE {
    int a;
    char b;
    float c;
}; // 未创建任何变量
struct SIMPLE x; // 声明变量
struct SIMPLE y[20], *z;

/* 常见用法 这个技巧和声明一个结构标签的效果几乎相同 */
typedef struct { // typedef创建一种新的类型
    int a;
    char b;
    float c;
} Simple; // Simple是类型名
Simple x;
Simple y[20], *z;
```
- ##### 结构成员
  一个结构的成员的名字可以和其他结构的成员的名字相同。

1. 直接访问
结构变量的成员是通过点操作符（.）访问的。
```c
sturct COMPLEX {
    float f;
    int a[20];
    long *lp;
    struct SIMPLE s;
    struct SIMPLE sa[10];
    struct SIMPLE *sp;
};
struct COMPLEX comp;

/* 访问 */
// 下标引用和点操作符具有相同优先级，结合性从左到右
// (comp.s).a 简化为 comp.s.a
// ( (comp.a)[4] ).c 简化为 comp.a[4].c 
```
2. 间接访问
拥有指向结构的指针，可通过对指针执行间接访问操作符，获得结构。
```c
void func( struct COMPLEX *cp );

(*cp).f // 访问这个变量所指向的结构的成员f
cp->f // 同上
```
- ##### 结构自引用
  一个结构内部包含一个**指向该结构本身的指针**，它事实上所**指向**的是**同一种类型的不同结构**。
1. 正确用法
```c
struct SELF_REF1 {
    int a;
    struct SELF_REF1 *b;
    int c;
};
```
2. 陷阱 1
```c
// 成员 b 是一个完整的结构，其内部还将包含它自己的成员 b，重复永无止境。
struct SELF_REF2 {
    int a;
    struct SELF_REF2 b;
    int c;
};
```
3. 陷阱 2
```c
// 这个声明的目的为这个结构创建类型名 SELF_REF3，类型名直到声明的末尾才定义。
// 所以在结构声明的内部它尚未定义。
typedef struct {
    int a;
    struct SELF_REF3 *b;
    int c;
} SELF_REF3;

// 解决方案是定义一个结构标签来声明 b。
typedef struct SELF_REF3_TAG {
    int a;
    struct SELF_REF3_TAG *b;
    int c;
} SELF_REF3;
```
- ##### 不完整声明（incomplete declaration）
  在 A 的成员列表中需要标签 B 的不完整声明，一旦 A 被声明之后，B 的成员列表也可以被声明。
```c
struct B;
struct A {
    struct B *partner;
};
struct B {
    struct A *partner;
};
```
- ##### 结构的初始化
```c
struct INIT_EX {
    inr a;
    short b[10];
    Simple c;
} x = {
    10,
    { 1, 2, 3, 4, 5 },
    { 25, 'x', 1.9 }
};
```
- ##### 结构、指针和成员
  直接或通过指针访问结构

- ##### 结构的存储分配
  编译器按照成员列表的顺序一个接一个地给每个成员分配内存。

  只有当存储成员时需要满足正确的边界对齐要求时，成员之间才可能出现用于填充地额外内存空间。

> 减少因边界对齐而造成的内存损失
> 可以使用`offsetof`宏（定义于`stddef.h`）
> `offsetof( type, member )`
> `type`是结构的类型，`member`是成员名，表达式的结果是`size_t`值
> 表示这个指定成员开始存储的位置距离结构开始存储的位置偏移几个字节。

C语言的参数传值调用方式要求把参数的一份副本传递给函数，这样效率低。
传递给函数一个指向结构的指针，指针比结构小得多，把它压到堆栈上效率能提高很多。

- ##### 位段（bit field）

  位段的声明和结构类似，但它的成员是一个或多个位的字段

> 位段成员必须声明为`int`、`signed int`或`unsigned int`类型
> 在成员名后是一个冒号和一个整数，这个整数指定该位段所占用的位的数目
```c
struct CHAR {
    unsigned ch   : 7;
    unsigned font : 6;
    unsigned size : 19;
};
struct CHAR ch1;
```

- ##### 联合（union）

  联合的所有成员引用的是内存的相同位置，在不同时刻把不同的东西存储在同一位置。
```c
union {
    float f;
    int i;
} fi;
```
联合变量可以被初始化，但这个初始值必须是联合第一个成员的类型，而且它必须位于一对花括号里面。
```c
union {
    int a;
    float b;
    char c[4];
} x = { 5 };
```

#### 11. 动态内存分配

- ##### malloc 和 free
C 函数库提供了`malloc`和`free`两个函数，分别用于执行动态内存分配和释放。
`malloc`从内存池中提取一块合适的内存，并向该程序返回一个指向这块内存的指针。
当一块以前分配的内存不再使用时，程序调用`free`函数把它归还给内存池供以后之需。
```c
/* 函数原型 */
void *malloc( size_t size ); // size_t，无符号类型，定义于 stdlib.h
void free( void *pointer );
```
`malloc`的参数是需要分配的内存字节数，且分配的是连续的内存。
如果内存池可以满足需求，则`malloc`返回一个指向被分配的内存块起始位置的指针。
如果内存池无法满足需求，则返回一个`NULL`指针。

`free`的参数必须要么是`NULL`，要么是一个先前从`malloc`、`calloc`或`realloc`返回的值。
标准表示一个`void *`类型的指针可以转换为其他任何类型的指针。

- ##### calloc 和 realloc
```c
void *calloc( size_t num_elements, size_t element_size );
void realloc( void *ptr, size_t new_size );
```

#### 12. 使用结构和指针

- ##### 链表
- ##### 单链表
- ##### 双链表


#### 13. 高级指针话题

- ##### 指向指针的指针
```c
int i;
int *pi;
int **ppi;
ppi = &pi; // 把 ppi 初始化为指向变量 pi
*ppi = &i; // 把 pi（通过 ppi 间接访问）初始化为指向变量 i
/* 下面各语句具有相同效果 */
i = 'a';
*pi = 'a';
**ppi = 'a';
```
- ##### 高级声明
```c
int *g; // 一个指向整型的指针，把表达式 *g 声明为一个整数
int f;  // 一个整型变量
/* 上下声明等价 */
int *g, f; // 并没有声明两个指针

int *f();    // f 是一个函数，它的返回值类型是一个指向整型的指针
int (*f)();  // f 是一个函数指针，它所指向的函数返回一个整型值
int *(*f)(); // f 是一个函数指针，它所指向的函数返回一个整型指针

int f[];  // f 是一个数组，它的元素类型是整型，即为整型数组
int *f[]; // f 是一个数组，它的元素类型是指向整型的指针

/* 非法，函数只能返回标量值，不能返回数组 */
int f()[]; // f 是个函数，它的返回值是一个整型数组
/* 非法，数组元素必须具有相同的长度，但不同的函数显然不可能具有不同的长度 */
int f[](); // f 似乎是个数组，它的元素类型是返回值为整型的函数

int (*f[])();
int *(*f[])();

int (*f)( int, float );
int *(*g[])( int, float )
```
- ###### 函数指针

  函数指针常见的两个用途是转换表（jump table）和作为参数传递给两外一个函数。


```c
/* 初始化函数指针 */
int f( int );
int (*pf)( int ) = &f;
// 函数名被使用时总是由编译器把它转化为函数指针。
// & 操作符只是显式地说明了编译器将隐式执行的任务。

/* 在函数指针被声明并被初始化之后，可使用 3 种方式调用函数 */
int ans;
ans = f( 25 );
ans = (*pf)( 25 );
ans = pf( 25 );
```
回调函数
转移表

- ##### 命令行参数
  C 程序的main函数具有两个形参。
  第 1 个通常为argc，它表示命令行参数的数目
  第 2 个通常为argv，它指向一组参数值（本质上指向参数数组的第一个元素）
```c
int main( int argc, char **argv )
```
- ##### 字符串常量

#### 14. 预处理器

- ##### 预定义符号

|符号|示例值|含义|
|-|-|-|
|`__FILE__`|"name.c"|进行编译的源文件名|
|`__LINE__`|25|文件当前行的行号|
|`__DATE__`|"Jan 31 1997"|文件被编译的日期|
|`__TIME__`|"18:04:30"|文件被编译的时间|
|`__STDC__`|1|如果编译器遵循 ANSI C，其值为 1，否则未定义|

- ##### `#define`
- 
每当有符号`name`出现在这条指令后面，预处理器就会把它替换为`stuff`。
```c
#define name stuff // 为数值命名一个符号
```

如果定义中的`stuff`非常长，它可以分成几行，除了最后一行，每行末尾加`\`。
```c
/* 这里是利用了“相邻的字符串常量被自动连接为一个字符串”这个特性 */
#define DEBUG_PRINT printf( "File %s line %d:" \
                        " x=%d, y=%d, z=%d", \
                        __FILE__, __LINE__, \
                        x, y, z )
```

使用`#define`指令，可以把任何文本替换到程序中。
```c
#define reg register // 为关键字 register 创建一个简短的别名 reg
#define do_forever for( ; ; )
#define CASE break;case
```

允许把任何参数替换到文本中，这种实现称为宏（macro）或定义宏（defined macro）。
```c
#define name(parameter-list) stuff
// parameter-list（参数列表）是由一个逗号分隔的符号列表
// 参数列表的左括号必须与 name 紧邻

#define SAQUARE(x) x * x
SAQUARE( 5 ) // 替换为 5 * 5
/* 问题点 */
SAQUARE( 3 + 1 ) // 替换为 3 + 1 * 3 + 1

/* 应改为 */
#define SAQUARE(x) (x) * (x)
```

**其他......**

- ##### 条件编译
constant-expression（常量表达式）由预处理器进行求值。
如果它的值是非零值（真），那么 statements 部分就被正常编译。
否则预处理器就静默地删除它们。
```c
#if constant-expression
    statements
#endif
```
**其他......**

- ##### 文件包含
  
**其他......**
  
- ##### 其他指令
  
**其他......**

#### 15. 输入/输出函数

**其他......**

#### 16. 标准函数库

**其他......**

#### 17. 经典抽象数据类型

**其他......**

#### 18. 运行时环境

**其他......**

### C++
(Related contents)
### Python
(Related contents)

## Operating Systems  
Operating System Fundamentals
(Related contents)
- [Real-Time OS](#real-time-os)
- [Embedded Linux](#embedded-linux)

### Real-Time OS
(Related contents)

- [FreeRTOS](#freertos)

#### FreeRTOS

学习[FreeRTOS官网](https://www.freertos.org/zh-cn-cmn-s "https://www.freertos.org/zh-cn-cmn-s")内容。


(Related contents)

### Embedded Linux
(Related contents)

## Microcontrollers
(Related contents)
- [GPIO](#gpio)  
- [ADC/DAC](#adcdac)    
- [Timers/Counters](#timerscounters)  
- [PWM](#pwm)  
- [Watchdog](#watchdog)  
- [Interrupts](#interrupts)  
- [DMA](#dma)    
- [Clock Management](#clock-management)  

### GPIO
(Related contents)
### ADC/DAC
(Related contents)
### Timers/Counters
(Related contents)
### PWM
(Related contents)
### Watchdog
(Related contents)
### Interrupts
(Related contents)
### DMA
(Related contents)
### Clock Management
(Related contents)

## Interfaces & Protocols
(Related contents)
- [Basic](#basic)
- [High-Speed](#high-speed)    
- [Wireless](#wireless)    
- [Industrial](#industrial)   
- [Network](#network) 
- [Automotive](#automotive)  
- [cellular](#cellular)  

### Basic
(Related contents)
- [UART](#uart)
- [I2C](#i2c)
- [SPI](#spi)

#### UART
(Related contents)
#### I2C
(Related contents)
#### SPI
(Related contents)

### High-Speed
(Related contents)
- [Ethemet](#ethemet)
- [USB](#usb)

#### Ethemet
(Related contents)
#### USB
(Related contents)

### Wireless
(Related contents)
- [BuleTooth](#buletooth)
- [Wi-Fi](#wi-fi)
- [LoRa](#lora)
- [Zigbee](#zigbee)
- [Thread](#thread)
- [Matter](#matter)
- [UWB](#uwb)

#### BuleTooth
(Related contents)
#### Wi-Fi
(Related contents)
#### LoRa
(Related contents)
#### Zigbee
(Related contents)
#### Thread
(Related contents)
#### Matter
(Related contents)
#### UWB
(Related contents)

### Industrial
(Related contents)

### Network
(Related contents)
- [TCP/IP](#tcpip)
- [UDP](#udp)

#### TCP/IP
(Related contents)
#### UDP
(Related contents)

### Automotive
(Related contents)
- [CAN](#can)
- [LIN](#lin)
- [MOST](#most)
- [FlexRay](#flexray)

#### CAN
(Related contents)
#### LIN
(Related contents)
#### MOST
(Related contents)
#### FlexRay
(Related contents)

### cellular
(Related contents)
- [GSM/LTE](#gsmlte)
- [LTE-M/5G](#lte-m5g)
- [NB-loT](#nb-lot)

#### GSM/LTE
(Related contents)
#### LTE-M/5G
(Related contents)
#### NB-loT
(Related contents)























