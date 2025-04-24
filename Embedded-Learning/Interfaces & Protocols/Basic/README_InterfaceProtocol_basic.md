### Basic
(Related contents)
- [UART](#uart)
- [I2C](#i2c)
- [SPI](#spi)

#### UART

The universal synchronous/asynchronous receiver transmitter (USART/UART) offers a flexible means of full-duplex data exchange with external equipment requiring an industry standard NRZ asynchronous serial data format. USART can operate with a very wide range of baud rates using a programmable baud rate generator.  
It supports synchronous one-way communication and half-duplex single-wire communication, as well as multiprocessor communications. It also supports the LIN (Local Interconnect Network), Smartcard protocol and IrDA (Infrared Data Association) SIR ENDEC specifications and Modem operations (CTS/RTS).  
High speed data communication is possible by using the DMA (direct memory access) for multibuffer configuration. Also, the UART can be used with interrupt.  
This article goes through the following UART features:  

- Simple UART communication in polling mode  
- UART with Interrupt  
- UART with DMA

#### I2C

I2C is a two-wire serial communication system used between integrated circuits which was originally created by Philips Semiconductors back in 1982.  
The I2C is a multi-master, multi-slave, synchronous, bidirectional, half-duplex serial communication bus.  

-   _**SDA (Serial Data)**_ is the line on which master and slave send or receive the information (sequence of bits).
-   _**SCL (Serial Clock)**_ is the clock-dedicated line for data flow synchronization.

[![i2c buq.png](https://wiki.st.com/stm32mcu/nsfr_img_auth.php/thumb/4/4f/i2c_buq.png/600px-i2c_buq.png)](https://wiki.st.com/stm32mcu/wiki/File:i2c_buq.png)  
SDA and SCL lines need to be pulled up with resistors. The value of these resistors depends on the bus length (the bus capacitance) and the transmission speed. The common value is 4.7kΩ. In any case, there are many guides to size them and we refer their reading to the more attentive reader.

#### 1.1. I2C Modes

-   _**Standard-Mode (Sm)**_ with a bit rate up to 100 kbit/s
-   _**Fast-Mode (Fm)**_ with a bit rate up to 400 kbit/s
-   _**Fast-Mode Plus (Fm+)**_ with a bit rate up to 1 Mbit/s

#### 1.2. I2C Frame

[![i2c trame.png](https://wiki.st.com/stm32mcu/nsfr_img_auth.php/thumb/c/c9/i2c_trame.png/500px-i2c_trame.png)](https://wiki.st.com/stm32mcu/wiki/File:i2c_trame.png)

-   Start Condition (S)
-   Stop Condition (P)
-   Repeated Start (Restart) Condition (Sr)
-   Acknowledge ACK (A)
-   Not Acknowledge NACK (/A)

#### 1.3. STM32 I2C Mode selection

The interface can operate in one of the four following modes:  

-   Slave transmitter
-   Slave receiver
-   Master transmitter
-   Master receiver  
    

#### 1.4. Main I2C HAL functions

Based on STM32Cube HAL functions, I2C data transfer can be performed in 3 modes: Blocking Mode, Interrupt Mode or DMA Mode  

-   **Blocking Mode:**  
    

The communication is performed in polling mode. The status of all data processing is returned by the same function after finishing transfer.  

HAL_I2C_Master_Transmit() 
HAL_I2C_Master_Receive()
HAL_I2C_Slave_Transmit()
HAL_I2C_Slave_Receive()
HAL_I2C_Mem_Write()
HAL_I2C_Mem_Read() 

-   **Non-blocking modes**

The communication is performed using Interrupts or DMA. These functions return the status of the transfer startup.  
The end of the data processing will be indicated through the dedicated I2C IRQ when using Interrupt mode or the DMA IRQ when using DMA mode.

-   **Interrupt Mode:**

HAL_I2C_Master_Transmit_IT()  
HAL_I2C_Master_Receive_IT()
HAL_I2C_Slave_Transmit_IT()  
HAL_I2C_Slave_Receive_IT() 
HAL_I2C_Mem_Write_IT()  
HAL_I2C_Mem_Read_IT()  

-   **DMA Mode:**

HAL_I2C_Master_Transmit_DMA()  
HAL_I2C_Master_Receive_DMA() 
HAL_I2C_Slave_Transmit_DMA() 
HAL_I2C_Slave_Receive_DMA()
HAL_I2C_Mem_Write_DMA()  
HAL_I2C_Mem_Read_DMA()

#### SPI
(Related contents)