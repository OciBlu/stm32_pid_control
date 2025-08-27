# stm32_pid_control
Controlling PID system using STM32

## MCU Configuration
RCC
- HSE: Crystal/Ceramic Resonator
- LSE: Disable
  
SYS
- Debug: Serial Wire
- Timebase Source: SysTick
  
UART1
- Mode: Asynchronous
- Hardware Flow Control (RS232): Disable
  
ADC1 Setting
- Mode: IN0=chek 
- Scan Conversion Mode = Enable
- Continous Conversion Mode = Enable
- Rank Sampling Time = Sama
- DMA Setting : Add ADC DMA, Mode= Circular, Increment address= Memory, Data Width= Half Time.
- NVIC Setting : Global Interrupt = Chek, ADC Interrupt = Chek
  
System Core / NVIC Interrupt Table / ADC Global Interrupt
- Preemtion Priority = 1

GPIO Setting
- PB12 Output