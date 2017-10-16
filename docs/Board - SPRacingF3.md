# Board - Seriously Pro SP Racing F3 (Acro/Deluxe)

Seriously Pro Racing F3 보드 (SPRacingF3)는 Cleanflight를 위해 특별히 설계된 최초의 보드입니다.

SeriouslyPro / SP 레이싱 및 공식 판매점에서 보드를 직접 구매하면 Cleanflight 개발에 자금을 지원할 수 있으므로 이것이 Seriously Pro 보드가 존재하는 이유입니다! 공식 판매점은 항상 SeriouslyPro.com 웹 사이트에 있습니다.

웹 사이트에서 전체 세부 정보를 볼 수 있습니다.

http://seriouslypro.com/spracingf3

## 하드웨어 특징

* 주변기기 지원 IO, ( ex. OSD + SmartPort + SBus + GPS + LED 스트립 + 베터리 모니터 + 초음파 센서 + 8 모터 )
* 하드웨어 플로팅 지점을 갖추고 효율적인 비행 계산이 가능한 STM32 F3 프로세서 사용
* 적층 설계 - OSD 및 ESC를 통합할 수 있는 완벽한 설계
* ESCs, Servos 와 레거시 수신기에 대한 16개의 I/O 포트, 8개의 핀 헤더를 통해 사용할 수 있습니다.
* SBus, SumH, SumD, Spektrum1024/2048, XBus, PPM, PWM 리시버등 다양한 규격의 포트를 지원 ( 외부 인버터가 필요하지 않음 | 벌트인 ).
* 프로그래밍이 가능한 LED, 레이스 및 야간 비행에 적합.
* OLED 를 위한 전용 I2C 포트.
* 베터리 모니터링을 위한 전압, 전류 포트.
* 비행에 관련된 위험, 알림 신호를 위한 부저 포트.
* 초음파 센서, PPM, RSSI, Current, GPIO, LED 스트립, 3.3v 을 위한 솔더 패드, 
* 개발자를 위한 디버깅 포트 지원 (SWD, 부트모드)
* 깔끔한 배선을위한 대칭 디자인.

## 시리얼 포트

| Value | Identifier   | RX           | TX           | 5v Tolerant | Notes                                                                                       |
| ----- | ------------ | ------------ | ------------ | ----------- | ------------------------------------------------------------------------------------------- |
| 1     | USART1       | PA10         | PA9          | YES         | CP2102 IC 를 통해 USB 포트에 내부적으료 연결되어있음, USART1 JST 커넥터에서도 사용 가능 |
| 2     | USART2       | PA15         | PA14         | YES         | USART2 JST 포트에서 사용 가능. |
| 3     | USART3       | PB11 / IO2_3 | PB10 / IO2_4 | NO          | IO_2 에서 사용 가능, UART3 JST 포트에서 사용 가능 |

* SWD와 USART2는 동시에 사용할 수 없습니다.

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

이 포트는 UART2 와 동시에 사용할 수 없습니다.

| Pin | Function       | Notes                                        |
| --- | -------------- | -------------------------------------------- |
| 1   | Ground         |                                              |
| 2   | NRST           |                                              |
| 3   | SWDIO          |                                              |
| 4   | SWDCLK         |                                              |

