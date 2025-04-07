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
> 学习书籍《C和指针》（Pointers On C）

1. [快速上手](#1.-快速上手)
2. [基本概念](#基本概念)
3. [数据](#数据)
4. [语句](#语句)
5. [操作符和表达式](#操作符和表达式)
6. [指针](#指针)
7. [函数](#函数)
8. [数组](#数组)
9. [字符串、字符和字节](#字符串、字符和字节)
10. [结构和联合](#结构和联合)
11. [动态内存分配](#动态内存分配)
12. [使用结构和指针](#使用结构和指针)
13. [高级指针话题](#高级指针话题)
14. [预处理器](#预处理器)
15. [输入/输出函数](#输入/输出函数)
16. [标准函数库](#标准函数库)
17. [经典抽象数据类型](#经典抽象数据类型)
18. [运行时环境](#运行时环境)

#### 1. 快速上手

> 1.1 空白和注释  

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

> 1.2 预处理指令

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























