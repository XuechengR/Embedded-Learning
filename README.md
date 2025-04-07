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
学习书籍《[Hello 算法](https://www.hello-algo.com/ "Hello 算法")》

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

**时间复杂度排序**：$O(1) < O(\log n) < O(n) < O(n \log n) < O(n^2) < O(2^n) < O(n!)$


#### 3. 数据结构
#### 4. 数组与链表
#### 5. 栈和队列
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
- [FreeRTOS](#freertos)
#### FreeRTOS
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























