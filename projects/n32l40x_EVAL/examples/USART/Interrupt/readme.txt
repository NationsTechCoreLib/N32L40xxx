1、功能说明

    该测例演示了USARTy与USARTz间通过中断实现的基础通信。
    USARTy发送TxBuffer1数据至USARTz，USARTz接收数据存至RxBuffer2。同时，
USARTz发送TxBuffer2数据至USARTy，USARTy接收数据存至RxBuffer1。
    随后，分别比较两组接收数据与发送数据，比较结果存入TransferStatus1变量
和TransferStatus2变量。
    USARTy和USARTz可以是USART1和USART2、USART3和UART4或UART4和UART5。


2、使用环境

	软件开发环境：KEIL MDK-ARM Professional Version 5.26.2.0

        硬件环境：最小系统板N32L40XML-STB_V1.0


3、使用说明
	
    系统时钟配置如下：
    - 时钟源 = HSE + PLL
    - 系统时钟 = 64MHz
    
    USART配置如下：
    - 波特率 = 115200 baud
    - 字长 = 8数据位
    - 1停止位
    - 校验控制禁用
    - 硬件流控制禁用（RTS和CTS信号）
    - 接收器和发送器使能
    
    USART引脚连接如下：
    - USART1_Tx.PA9    <------->   USART2_Rx.PB5
    - USART1_Rx.PA10   <------->   USART2_Tx.PB4 
    或
    - USART3_Tx.PC10   <------->   UART4_Rx.PD12
    - USART3_Rx.PC11   <------->   UART4_Tx.PD13
    或
    - UART4_Tx.PC10    <------->   UART5_Rx.PB9
    - UART4_Rx.PC11    <------->   UART5_Tx.PB8

    
    测试步骤与现象：
    - Demo在KEIL环境下编译后，下载至MCU
    - 复位运行，依次查看变量TransferStatus1和TransferStatus2，其中，
      PASSED为测试通过，FAILED为测试异常


4、注意事项

1. Function description

    This test case demonstrates the basic communication between USARTy and USARTz through interrupts.
    USARTy sends TxBuffer1 data to USARTz, and USARTz receives data to RxBuffer2. at the same time,
USARTz sends TxBuffer2 data to USARTy, and USARTy receives data to RxBuffer1.
    Subsequently, the two groups of received data and sent data are compared respectively, and the comparison 
	results are stored in the TransferStatus1 variable and the TransferStatus2 variable.
    USARTy and USARTz can be USART1 and USART2, USART3 and UART4 or UART4 and UART5.


2. Use environment

        Software development environment: KEIL MDK-ARM Professional Version 5.26.2.0

        Hardware environment: minimum system board N32L40XML-STB_V1.0


3. Instructions for use

    The system clock configuration is as follows:
    -Clock source = HSE + PLL
    -System clock = 64MHz
    
    The USART configuration is as follows:
    -Baud rate = 115200 baud
    -Word length = 8 data bits
    -1 stop bit
    -Verification control disabled
    -Hardware flow control disabled (RTS and CTS signals)
    -Receiver and transmitter enable
    
    The USART pin connections are as follows:
    -USART1_Tx.PA9 <-------> USART2_Rx.PB5
    -USART1_Rx.PA10 <-------> USART2_Tx.PB4
    or
    -USART3_Tx.PC10 <-------> UART4_Rx.PD12
    -USART3_Rx.PC11 <-------> UART4_Tx.PD13
    or
    -UART4_Tx.PC10 <-------> UART5_Rx.PB9
    -UART4_Rx.PC11 <-------> UART5_Tx.PB8

    
    Test steps and phenomena:
    -After the Demo is compiled in the KEIL environment, download it to the MCU
    -Reset operation, check the variables TransferStatus1 and TransferStatus2 in turn, among them,
      PASSED means the test passed, FAILED means the test is abnormal


4. Matters needing attention