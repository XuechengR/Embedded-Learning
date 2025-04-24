## Microcontrollers
Learning based on [STM](https://www.st.com.cn "https://www.st.com.cn") official website.

### Simple definition of a Microcontroller

A microcontroller (also called _**μC**_ or _**MCU**_) is an embedded computer chip that controls most of the electronic gadgets and appliances people used on a daily basis.  
It is a compact integrated circuit designed to govern a specific operation in an embedded system.

### Microcontroller architecture

A typical microcontroller includes a processor, memory and Input/Output (I/O) peripherals on a single chip. Its components may be extended to include: Digital I/O, Analog I/O, Timers, Communication interfaces, Watchdog (a timer that is responsible for the detection of timed out or locked instruction)...  
**A processor** is a little chip present in the device that has the role of arranging the instructions and order the outputs. The manufacturer defines the integrated peripherals and the hardware capabilities. This is the basic layout of a microcontroller:  
[![newchart.jpg](https://wiki.st.com/stm32mcu/nsfr_img_auth.php/thumb/3/34/newchart.jpg/500px-newchart.jpg)](https://wiki.st.com/stm32mcu/wiki/File:newchart.jpg)


- [GPIO](#gpio)  
- [ADC/DAC](#adcdac)    
- [Timers/Counters](#timerscounters)  
- [PWM](#pwm)  
- [Watchdog](#watchdog)  
- [Interrupts](#interrupts)  
- [DMA](#dma)    
- [Clock Management](#clock-management)  

### GPIO

**GPIO** stands for **general purpose input/output**. It is a type of pin found on an integrated circuit that does not have a specific function. While most pins have a dedicated purpose, such as sending a signal to a certain component, the function of a GPIO pin is customizable and can be controlled by the software.  

- **Pin Mode** : Each port bit of the general-purpose I/O (GPIO) ports can be individually configured by software in several modes:  
    - input or output
    - analog
    - alternate function (AF).
-  **Pin characteristics** :
    - Input : no pull-up and no pull-down or pull-up or pull-down
    - Output : push-pull or open-drain with pull-up or pull-down capability
    - Alternate function : push-pull or open-drain with pull-up or pull-down capability.

[![GPIO Functional description graph.png](https://wiki.st.com/stm32mcu/nsfr_img_auth.php/a/a0/GPIO_Functional_description_graph.png)](https://wiki.st.com/stm32mcu/wiki/File:GPIO_Functional_description_graph.png)

### ADC/DAC

A digital to analog converter is a system that converts a digital input signal or a value into an analog signal. It takes in a digital number or value as an input and converts it into an analog voltage. The voltage level corresponds to the binary number in the DAC output register.

(Related contents)
### Timers/Counters
(Related contents)
### PWM
(Related contents)
### Watchdog

**WDG** stands for **watchdog**. The main goal of this IP is to detect and resolve malfunctions due to software failures. The principle is to periodically refresh the WDG (or pet the dog), if the counter isn't refreshed, a system reset is generated. Also, the WDG acts as a protection since it avoids to stay stuck in a particular stage of processing. The configuration using option bytes can launch the WDG by hardware or software. Once enabled, it can only be disabled by a reset

> [!Information]
> The WDG (or the dog) needs to be refreshed (pet) or the system will be reset (bark)

#### WDG type

There are two types of WDG :

- [WWDG](#wwdg--window-watchdog) : Window watchdog
- [IWDG](#iwdg--independent-watchdog) : Independent watchdog

##### WWDG : Window watchdog

###### Definition

The window watchdog is based on a 7-bit downcounter that can be set as free running. It can be used as a watchdog to reset the device when a problem occurs. It is clocked from the main clock. It has an early warning interrupt capability and the counter can be frozen in debug mode.

##### Application benefits

- Best suited for applications which require the watchdog to react within an accurate time window.
- Configurable time-window thanks to the prescaler value (For example, the STM32L476xx have a programmable timeout range from 51.2 us to 28.2ms)
- Selectable hardware or software start
- Early Wakeup Interrupt (EWI) available before reset happens

###### How does it work ?

The diagram below illustrates how the WWDG operates. If the downcounter is reloaded too early or too late, the window watchdog will initiate a reset.

[![WWDG Refresh.png](https://wiki.st.com/stm32mcu/nsfr_img_auth.php/thumb/e/e8/WWDG_Refresh.png/900px-WWDG_Refresh.png)](https://wiki.st.com/stm32mcu/wiki/File:WWDG_Refresh.png)

As can be seen on the following block diagram, the counter value and the window value are compared in order to evaluate the time to refresh the downcounter in the configurable window.

[![WWDG.png](https://wiki.st.com/stm32mcu/nsfr_img_auth.php/thumb/e/e7/WWDG.png/800px-WWDG.png)](https://wiki.st.com/stm32mcu/wiki/File:WWDG.png)

##### IWDG : Independent Watchdog

###### Definition

The independent watchdog is based on a 12-bit downcounter and 8-bit prescaler. It is clocked from an independent 32 kHz internal RC (LSI) and as it operates independently from the main clock, it can operate in Stop and Standby modes. It can be used either as a watchdog to reset the device when a problem occurs, or as a free running timer for application timeout management. It is hardware or software configurable through the option bytes. The counter can be frozen in debug mode.

###### Application benefits

- Totally **independent** process outside the main application
- Configurable timeout period thanks to the prescaler value (For example, the STM32L476xx have a programmable timeout range from 125us to 32.7s)
- Selectable hardware or software start
- Selectable low-power freeze in Standbye or Stop modes

###### How does it work ?

The IWDG architecture is represented below : [![IWDG.png](https://wiki.st.com/stm32mcu/nsfr_img_auth.php/0/08/IWDG.png)](https://wiki.st.com/stm32mcu/wiki/File:IWDG.png)

As can be seen on the block diagram above, IWDG registers are located in the CORE voltage domain while its functions are in the VDD voltage domain. The 8-bit prescaler is used to **divide the LSI oscillator frequency.** When the IWDG is started, the 12-bit counter starts counting down from the reset value of 0xFFF. To refresh the IWDG counter, the **Key value** (0xAAAA) must be written in the Key register to reload the counter value. If the downcounter reaches the end of the count value (0x000), a system reset is generated.

> [!Information]
> For more details, check the dedicated IWDG chapter in the product reference manual.

### Interrupts
(Related contents)

### DMA

_**DMA**_ stands for Direct Memory Access controller.  
DMA is a bus master and system peripheral providing high-speed data transfers between peripherals and memory, as well as memory-to-memory.  
Data can be quickly moved by DMA _**without any CPU action**_, keeping CPU resources free for other operations.  

This article uses the STM32L476 device as an example. The STM32L476 device embeds 2 DMAs: DMA1 and DMA2.  

Each channel is dedicated to managing memory access requests from one or more peripherals. The two DMA controllers have 14 channels in total. Each channel is dedicated to managing memory access requests from one or more peripherals. Each channel has an arbiter to handle priority between DMA requests.

|     |     |     |
| --- | --- | --- |
| **DMA features** | DMA1 | DMA2 |
| **Number of regular channels** | 7   | 7   |