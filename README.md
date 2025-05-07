# os
## 1. 계좌 Race Condition + Deadlock 과제
📌 과제명
동기화 문제 해결: 은행 계좌 이체 시스템 구현과 Deadlock 회피

### 과제 목적
Race condition과 deadlock 문제를 이해하고 해결 방법을 직접 구현해본다.

synchronized, Lock, ReentrantLock, wait/notify 등을 활용해 본다.

### 요구사항
N개의 은행 계좌가 존재함 (BankAccount 클래스).

다수의 쓰레드가 무작위로 서로 간의 금액을 이체함.

Race condition 발생 시 시뮬레이션 오류가 발생해야 함 (예: 총합 일치 안함).

Deadlock을 의도적으로 유발하거나 회피하는 코드를 실험할 수 있어야 함.

다음 기능을 분리하여 구현할 것:

동기화 없는 이체 (unsynchronizedTransfer)

synchronized 기반 이체 (synchronizedTransfer)

ReentrantLock 기반 이체 (lockedTransfer)

Deadlock 회피 로직 (deadlockSafeTransfer)

최종적으로 은행 전체의 총액은 변화가 없어야 함.

### 평가 포인트
동시성 문제 재현 및 해결 능력

코드 설계의 가독성

Thread-safe 설계 및 동기화 전략 선택 이유

## 2. 식사하는 철학자 문제
### 과제명
동시성 제어: 식사하는 철학자 문제 시뮬레이터 구현

### 과제 목적
자원 경합, 교착 상태(deadlock), 기아 상태(starvation) 등의 문제를 이해한다.

동기화 기법을 선택하고 그 이유를 설명할 수 있어야 한다.

### 요구사항
철학자는 5명. 각각 좌우의 젓가락이 있어야 식사할 수 있음.

각 철학자 쓰레드는 생각 -> 젓가락 집기 -> 식사 -> 젓가락 놓기 순서로 반복함.

아래의 동기화 전략을 구현 및 비교:

단순 synchronized

Semaphore

왼쪽 젓가락부터 잡는 철학자 vs 오른쪽부터 잡는 철학자 혼합 전략

자원 순서 고정 방식 (deadlock 방지)

GUI 또는 로그 기반 상태 출력 (예: "철학자 1이 식사 중")

철학자 모두가 일정 시간 이상 굶지 않도록 설계할 것.

### 평가 포인트
deadlock과 starvation 방지 여부

동기화 전략의 명확한 설명

동작 로그 혹은 시각화 결과

## 3. 생산자-소비자 패턴
### 과제명
버퍼 공유 동기화: 생산자-소비자 시뮬레이션

### 과제 목적
공유 자원 접근을 조율하는 방식(wait/notify, BlockingQueue, Semaphore) 실습

동기화와 멀티스레드 설계에 대한 이해 증진

### 요구사항
생산자 N명, 소비자 M명. 모두 쓰레드로 동작.

공유 버퍼(큐)의 크기는 고정된 MAX_CAPACITY.

생산자는 버퍼가 가득 찼을 때 대기해야 함.

소비자는 버퍼가 비었을 때 대기해야 함.

아래 방식 중 2가지 이상으로 구현:

wait/notify

BlockingQueue

Semaphore 기반

콘솔에 생산/소비 이벤트가 출력되도록 할 것.

### 평가 포인트
자원 접근의 적절한 동기화

다양한 동기화 기법 비교 및 설명

에러/데드락 없이 잘 작동하는지
