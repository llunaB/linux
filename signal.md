# signal

## signal?

- Thread / Process 에게 정보를 전달하는 신호

- 리눅스에서는 최대 256개 신호 전달이 가능하다.

  - 시그널 종류 : kill -l

- 단순 정보를 보낼 때 사용한다.

  - 더 많은 정보를 보내고 싶다면 Socket, IPC 사용

  



# Interrupt

- CPU 동작 중, 하던 일을 멈추고 처리하도록 하는 것

- 인터럽트 발생 시 예약된 함수가 동작한다.



## ISR(Interrupt Service Routine)

- 인터럽트에 대응하여 호출되는 코드
- 인터럽트 핸들러라고 불린다.



## 인터럽트 종류

### 리눅스 Signal 발생

- SW Interrupt 가 발생하여 하던 일을 멈추고 지정된 Handler 함수가 즉시 호출됨
- 핸들러 미지정시 커널 내부에서 Default 동작을 수행



# Signal API

## Signal 로 인한 S/W 발생시 Handler 호출

- 핸들러 등록 함수 이름 : signal(시그널 번호, 핸들러 이름);
- 매크로들이 모두 등록되어 있음



## SIGUSR1

- User Signal 정해진 역할 없음
- kill 또는 killall 명령어로 시그널 전송 가능

```bash
kill -SIGUSR1 [PID]
killall -SIGUSR1 [process이름]
```





# Nested Interrupt

인터럽트 도중에 인터럽트 발생



## Interrupt 주의

- ISR과 일반 함수 모두 같은 전역변수를 사용하는 경우 코드에 버그가 발생할 수 있음
- 도중에 인터럽트가 발생하면 안되는 곳에 Interrupt Disable 처리를 해야 함

![Interrupt_disable](Signal.assets/Interrupt_disable.jpg)