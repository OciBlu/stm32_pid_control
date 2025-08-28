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

TIM2 (PWM Setting output)
- CH2 = PWM Generator CH2
- Prescaler = 0
- Counter Mode = UP
- Counter Periode (Auto Reload Register) = 255
- Internal Clock Division = No Division
- auto-reload preload = Disable

## Catatan
- PWM Frequency = System Clock Frequency /(Prescaler+1)×(ARR+1)
- The maximum prescaler and ARR value in an STM32 is 65535 for a 16-bit timer