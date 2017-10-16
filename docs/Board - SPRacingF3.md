# Board - Seriously Pro SP Racing F3 (Acro/Deluxe)

Seriously Pro Racing F3 보드 (SPRacingF3)는 Cleanflight를 위해 특별히 설계된 최초의 보드입니다.

SeriouslyPro / SP 레이싱 및 공식 판매점에서 보드를 직접 구매하면 Cleanflight 개발에 자금을 지원할 수 있으므로 이것이 Seriously Pro 보드가 존재하는 이유입니다! 공식 판매점은 항상 SeriouslyPro.com 웹 사이트에 있습니다.

웹 사이트에서 전체 세부 정보를 볼 수 있습니다.

http://seriouslypro.com/spracingf3

## 하드웨어 특징

* 주변기기 지원 IO, ( ex. OSD + SmartPort + SBus + GPS + LED 스트립 + 베터리 모니터 + 초음파 센서 + 8 모터 )
* On-board high-capacity black box flight log recorder - optimize your tuning and see the results of your setup without guesswork. (Acro and Deluxe)
* 하드웨어 플로팅 지점을 갖추고 효율적인 비행 계산이 가능한 STM32 F3 프로세서 사용
* Stackable design - perfect for integrating with OSDs and power distribution boards.
* 16 PWM I/O lines for ESCs, Servos and legacy receivers. 8 available on standard pin headers. 8 via side mounted connectors.
* Supports SBus, SumH, SumD, Spektrum1024/2048, XBus, PPM, PWM receivers. No external inverters required (built-in).
* Dedicated output for programmable LEDs - great for orientation, racing and night flying.
* Dedicated I2C port for connection of OLED display without needing flight battery.
* Battery monitoring ports for voltage and current.
* Buzzer port for audible warnings and notifications.
* Solder pads in addition to connectors for Sonar, PPM, RSSI, Current, GPIO, LED Strip, 3.3v, 
* Developer friendly debugging port (SWD) and boot mode selection, unbrickable bootloader.
* Symmetrical design for a super tidy wiring.
* Wire up using using pin headers, JST-SH sockets or solder pads. Use either right-angled or straight pin-headers.
* Barometer mounted on the bottom of the board for easy wind isolation.

## Serial Ports

| Value | Identifier   | RX           | TX           | 5v Tolerant | Notes                                                                                       |
| ----- | ------------ | ------------ | ------------ | ----------- | ------------------------------------------------------------------------------------------- |
| 1     | USART1       | PA10         | PA9          | YES         | Internally connected to USB port via CP2102 IC.  Also available on a USART1 JST connector and on through hole pins. |
| 2     | USART2       | PA15         | PA14         | YES         | Available on USART2 JST port only. |
| 3     | USART3       | PB11 / IO2_3 | PB10 / IO2_4 | NO          | Available on IO_2, USART3 JST port and through hole pins. |

* You cannot use SWD and USART2 at the same time.
* You may encounter flashing problems if you have something connected to the USART1 RX/TX pins.   Power other devices off and/or disconnect them.

## Pinouts

자세한 내용은 다음과 같은 세부 정보를 참조하십시오.

http://seriouslypro.com/spracingf3#manual

### IO_1

The 8 pin IO_1 connector has the following pinouts when used in RX_PARALLEL_PWM mode.

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | Ground         |                                              |
| 2   | VCC_IN         | Voltage as-supplied by BEC.                  |
| 3   | RC_CH1         | |
| 4   | RC_CH2         | |
| 5   | RC_CH5         | |
| 6   | RC_CH6         | |
| 7   | LED_STRIP      | Enable `feature LED_STRIP`                   |
| 8   | VCC            | 3.3v output for LOW CURRENT application only |

When RX_PPM/RX_SERIAL is used the IO_1 pinout is as follows.

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | Ground         |                                              |
| 2   | VCC_IN         | Voltage as-supplied by BEC.                  |
| 3   | RX_PPM         | Enable `feature RX_PPM`                      |
| 4   | GPIO           |                                              | 
| 5   | SoftSerial1_RX |                                              | 
| 6   | SoftSerial1_TX |                                              | 
| 7   | LED_STRIP      | Enable `feature LED_STRIP`                   |
| 8   | VCC            | 3.3v output for LOW CURRENT application only |

### IO_2

The 8 pin IO_2 connector has the following pinouts when used in RX_PARALLEL_PWM mode.

| Pin | Function          | Notes                                        |
| --- | ----------------- | -------------------------------------------- |
| 1   | Ground            |                                              |
| 2   | VCC_IN            | Voltage as-supplied by BEC.                  |
| 3   | RC_CH3            |                                              |
| 4   | RC_CH4            |                                              |
| 5   | RC_CH7/SONAR_TRIG |                                              |
| 6   | RC_CH8/SONAR_ECHO |                                              |
| 7   | ADC_1             | Current Sensor                               |
| 8   | ADC_2             | RSSI                                         |

When RX_PPM/RX_SERIAL is used the IO_2 pinout is as follows.

| Pin | Function                  | Notes                                        |
| --- | ------------------------- | -------------------------------------------- |
| 1   | Ground                    |                                              |
| 2   | VCC_IN                    | Voltage as-supplied by BEC.                  |
| 3   | RX_SERIAL                 | UART3 RX                                     |
| 4   |                           | UART3_TX                                     | 
| 5   | SONAR_TRIG/SoftSerial2_RX | Enable `feature SONAR/SOFTSERIAL`     | 
| 6   | SONAR_ECHO/SoftSerial2_TX | Enable `feature SONAR/SOFTSERIAL`     | 
| 7   | ADC_1                     | Current Sensor                               |
| 8   | ADC_2                     | RSSI                                         |

### UART1/2/3

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | Ground         |                                              |
| 2   | VCC_IN         | Voltage as-supplied by BEC.                  |
| 3   | TXD            |                                              |
| 4   | RXD            |                                              |

### I2C

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | Ground         |                                              |
| 2   | 5.0v           | Voltage as-supplied by BEC OR USB, always on |
| 3   | SCL            |                                              |
| 4   | SDA            |                                              |

### SWD

The port cannot be used at the same time as UART2.

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | Ground         |                                              |
| 2   | NRST           |                                              |
| 3   | SWDIO          |                                              |
| 4   | SWDCLK         |                                              |

