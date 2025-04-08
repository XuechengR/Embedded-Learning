# Embedded-Learning
Self-taught embedded knowledge


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

##### 3.1 数据结构分类
逻辑结构：**线性**和**非线性**。
> 线性数据结构：**数组**、**链表**、**栈**、**队列**、**哈希表**，元素之间是**一对一**的顺序关系。
> 非线性数据结构：树、堆、图、哈希表。
> 
> 非线性数据结构可以进一步划分为**树形结构**和**网状结构**。
>> 树形结构：**树、堆、哈希表**，元素之间是**一对多**的关系。
>> 网状结构：**图**，元素之间是**多对多**的关系。

物理结构：连续与分散。

##### 3.2 基本数据类型
基本数据类型是 CPU 可以直接进行运算的类型。
> 整数类型 `byte`、`short`、`int`、`long` 。
> 浮点数类型 `float`、`double` ，用于表示小数。
> 字符类型 `char` ，用于表示各种语言的字母、标点符号甚至表情符号等。
> 布尔类型 `bool` ，用于表示“是”与“否”判断。

基本数据类型以二进制的形式存储在计算机中。
> 一个二进制位即为 1 比特。
> 1 字节（byte）由 8 比特（bit）组成。

##### 3.3 原码、反码和补码

数字是以“补码“的形式存储在计算机中的。
- 原码（sign-magnitude）：二进制表示的最高位为符号位，其中 $0$ 表正，$1$ 表负，其余位表示数字的值。
- 反码（1's complement）：正数的反码与其原码相同，负数的反码是**对其原码除符号位外的所有位取反**。
- 补码（2's complement）：正数的补码与其原码相同，负数的补码是**在其反码的基础上加 1** 。

1. 负数的原码不能直接用于运算，因此引入反码。
2. 数字零的原码有 $+0$ 和 $−0$ 两种表示方式，与原码一样，反码也存在正负零歧义问题，因此引入了补码。
3. 补码 $10000000$ 代表 $−128$

#### 4. 数组与链表

###### 4.1 数组
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

###### 4.2 链表
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

###### 5.1 栈

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

###### 5.2 队列

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
6. [指针](#6指针)
7. [函数](#7函数)
8. [数组](#8数组)
9. [字符串、字符和字节](#9字符串、字符和字节)
10. [结构和联合](#10-结构和联合)
11. [动态内存分配](#11-动态内存分配)
12. [使用结构和指针](#12-使用结构和指针)
13. [高级指针话题](#13-高级指针话题)
14. [预处理器](#14-预处理器)
15. [输入/输出函数](#15-输入/输出函数)
16. [标准函数库](#16-标准函数库)
17. [经典抽象数据类型](#17-经典抽象数据类型)
18. [运行时环境](#18-运行时环境)

#### 1. 快速上手

##### 1.1 空白和注释  

```c
/* 注释1 */
  
/* 
** 注释2
*/
 
// 注释3
```
**注释**（comment），注释以符号`/*`开始，以符号`*/`结束，**注释不能嵌套**。

```c
#if 0
    statements
#endif 
```
逻辑上删除一段代码，使用`#if`指令。

##### 1.2 预处理指令

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
这些声明被成为**函数原型**（function prototype）。其中的参数名字不是必须的，参数名的目的是提示它们的作用。

`rearrange`函数接收4个参数，第1个和第2个参数为**指针**（pointer）。

关键字`void`表示函数不返回任何值，无返回值的函数被称为**过程**（procedure）。

##### 1.3 main函数
==`main`函数，程序的起点。==


#### 2. 基本概念
> 组成一个程序的每个（或多个）源代码通过编译过程分别转换为**目标代码**（object code）。然后各个目标文件由**链接器**（linker）捆绑在一起，形成单一可执行程序。

源代码 编译 &rarr; 目标代码 与函数库 链接 &rarr; 可执行文件

> **预处理器**（preprocessor） &rarr; **解析**（parse）&rarr; **优化器**（optimizer）

预处理器 &rarr; 执行文本操作，替换
解析 &rarr; 产生绝大多数错误和警告
优化 &rarr; 处理目标代码，使它效率更高

==编译链接==

#### 3. 数据

##### 3.1 基本数据类型

- **整型**包括，字符，短整型，整型，长整型，都分**有符号**（singed）**和无符号**（unsigned）。

  长整型至少应该和整型一样长，而整型至少应该和短整型一样长。

- **字面值**（literal）等价字面值常量，不允许发生改变。命名常量是声明为`const`的变量。

  在整型字面值后面添加字符`L`和`l`，可以使这个整数被解释为`long`整型值。
  字符`U`或`u`则用于把数值指定为`unsigned`整型值。`UL`则为`unsigned long`整型值。

- **字符常量**：`'R'`，宽字符常量（wide character literal）：`L'R'`。

- **枚举**（enumerated）类型就是指它的值为符号常量而不是字面值类型。

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

- **浮点数**包括`float`、`double`、`long double`类型。

  浮点数字面值缺省的情况下都为double类型。后跟`L`或`l`，则表示为`long double`类型。后跟`F` 或`f`，则表示`float`类型。

- **指针**

  变量的值存储在计算机的内存中，每个变量都占据内存的一个特定的位置。每个内存位置都由地址唯一确定并引用。指针只是地址的另外一个名字，指针变量就是一个其值为另外一个（一些）内存地址的变量。

###### 3.2 基本声明

- **`typedef`**：为各种数据类型定义新名字。
```c
/* 声明一个指向char型数据的指针，指针名为ptr_to_char */
char *ptr_to_char;
/* 为 char * 类型，定义新名字为ptr_to_char */
typedef char * ptr_to_char;
/* 声明一个ptr_to_char类型的变量a */
ptr_to_char a;
```
- **常量**
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

##### 3.3 作用域
文件作用域，函数作用域，代码块作用域，原型作用域

##### 3.4 链接属性
external（外部），internal（内部），none(无)
- external：不论声明多少次，位于几个源文件都表示同一个实体。
- internal：在同一个源文件内的所有声明中都指向同一个实体，但位于不同源文件的多个声明则分属不同的实体。
- none：总是被当作单独的个体，多个声明被当作不同的独立实体。
```c
/* 被源文件私有 */
static int b;
/* 函数声明为static，防止它被其他源文件调用 */
static int c( int d ){}
```
`extern`和`static`
#### 4. 语句
(Related contents)
#### 5. 操作符和表达式
(Related contents)
#### 6. 指针
(Related contents)
#### 7. 函数
(Related contents)
#### 8. 数组
(Related contents)
#### 9. 字符串、字符和字节
(Related contents)
#### 10. 结构和联合
(Related contents)
#### 11. 动态内存分配
(Related contents)
#### 12. 使用结构和指针
(Related contents)
#### 13. 高级指针话题
(Related contents)
#### 14. 预处理器
(Related contents)
#### 15. 输入/输出函数
(Related contents)
#### 16. 标准函数库
(Related contents)
#### 17. 经典抽象数据类型
(Related contents)
#### 18. 运行时环境
(Related contents)

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
> “提供超越商业替代品用户所要求的质量和服务的免费产品”

15 多年来，FreeRTOS 专职开发人员一直与全球 顶尖的芯片公司紧密合作， 为客户提供[市场领先![external_link](https://www.freertos.org/svg/external_link.svg)](https://www.embedded.com/electronics-blogs/embedded-market-surveys/4458724/2017-Embedded-Market-Survey)以及 完全免费的商用级、[高品质](https://www.freertos.org/Documentation/02-Kernel/06-Coding-guidelines/02-FreeRTOS-Coding-Standard-and-Style-Guide) **RTOS**和工具……但 什么是 RTOS？

此页面首先介绍了操作系统的定义，接着具体定义了 [实时操作系统](https://www.freertos.org/Documentation/02-Kernel/01-About-the-FreeRTOS-kernel/01-FreeRTOS-kernel)，然后 更进一步定义了实时定时器内核（或实时执行器）。

另请参阅常见问题项目“[为什么用 RTOS](https://www.freertos.org/Why-FreeRTOS/FAQs/What-is-this-all-about#why-use-an-rtos)” ，了解有关在什么情况使用和为什么 在嵌入式系统软件设计中使用 RTOS 会有帮助。

## [](https://www.freertos.org/zh-cn-cmn-s/Why-FreeRTOS/What-is-FreeRTOS#%E4%BB%80%E4%B9%88%E6%98%AF%E9%80%9A%E7%94%A8%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F)什么是通用操作系统？

操作系统是支持计算机基本功能的计算机程序， 为在计算机上运行的程序（或_应用程序_）提供服务。应用程序提供计算机用户 想要或需要的功能。操作系统提供的服务使得应用程序写入更快、更简单、 并且更易于维护。如果您正在阅读此网页，说明您正在使用网络浏览器（提供您感兴趣的功能的应用程序 ），该浏览器本身会在操作系统提供的环境中运行 。

## [](https://www.freertos.org/zh-cn-cmn-s/Why-FreeRTOS/What-is-FreeRTOS#%E4%BB%80%E4%B9%88%E6%98%AF-rtos)什么是 RTOS？

大多数操作系统似乎能同时执行多个程序。这称为多任务处理。实际上， 每个处理器内核在任何给定时间点都只能运行一个执行线程。操作系统中 一个名为调度器的部分负责决定何时运行哪个程序， 并通过在每个程序之间快速切换以造成同时执行的假象。

操作系统的类型取决于调度器如何决定何时运行哪个程序。例如， 多用户操作系统（如 Unix）中使用的调度器将确保每个用户都能获得合理的处理时间 。再比如，桌面操作系统（如 Windows）中的调度器会努力确保计算机对用户作出响应。 （**注意：FreeRTOS 并非大型操作系统，也不是为在台式 计算机级处理器上运行而设计的，我使用这些例子纯粹是因为它们是读者熟悉的系统。**）

实时操作系统中的调度器旨在提供 可预测的（通常描述为 _确定性_）执行模式。这对嵌入式系统而言意义重大，因为嵌入式系统 经常有实时要求。实时要求是指定嵌入式系统 必须在严格定义的时间内（_截止时间_）响应某个事件。只有当操作系统调度器的行为 可以预测（因此具有确定性）时， 才能保证满足实时要求。

传统的小型实时调度器（如 [FreeRTOS](https://www.freertos.org/Documentation/02-Kernel/02-Kernel-features/01-Tasks-and-co-routines/04-Task-scheduling) 中使用的调度器） 通过允许用户为每个执行线程分配优先级来实现确定性。然后，调度器根据优先级来判断 下一个要运行的执行线程。在 FreeRTOS 中，执行线程称为 _任务_。

## [](https://www.freertos.org/zh-cn-cmn-s/Why-FreeRTOS/What-is-FreeRTOS#%E4%BB%80%E4%B9%88%E6%98%AF-freertos)什么是 FreeRTOS？

(另请参阅“[有关 FreeRTOS](https://www.freertos.org/Documentation/02-Kernel/01-About-the-FreeRTOS-kernel/01-FreeRTOS-kernel) 的更多信息”)

FreeRTOS 是 RTOS 的一个类别，设计得足够小，可以在微控制器上运行， 但其用途并不局限于微控制器应用程序。

微控制器是一种小型且资源有限的处理器， 在单个芯片上集成了处理器本身、 用于保存待执行程序的只读存储器（ROM 或闪存） 以及执行程序所需的随机存取存储器（RAM） 。通常情况下，程序是 直接从只读存储器中执行的。

微控制器通常用于深度嵌入式应用中（在这些应用中， 实际上看不到处理器本身，也看不到它们运行的软件）， 它们通常有非常具体和专门的工作要做。由于大小限制和专用终端应用的性质，很少有理由使用完整的 RTOS 实现， 或者说，使用完整的 RTOS 实现是不可能的。因此，FreeRTOS 只提供核心的实时调度功能、 任务间通信、定时和同步原语。这意味着 将它描述为实时内核或实时执行器更准确。其他功能，如命令控制台 接口或网络堆栈，可通过附加组件实现。
- [FreeRTOS](#freertos)
#### FreeRTOS
[](https://www.freertos.org/zh-cn-cmn-s "https://www.freertos.org/zh-cn-cmn-s")学习官网内容。



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























