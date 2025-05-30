# 스케줄링 : 비례배분

### 비례 배분 == 공정 배분
: 반환시간이나 응답시간을 최적화하는 대신 스케줄러가 각 작업에게 CPU의 일정 비율을 보장하는 것

-> 좋은 예 : 추첨 스케줄링

## 1. 추천 기법
장점 : 무작위성

(1) 추첨권 화폐
: 사용자가 추첨권을 자신의 화폐 가치로 추첨권을 자유롭게 할당할 수 있도록 허용한다. 시스템은 자동적으로 화폐 가치를 변환한다.

(2) 추첨권 양도
: 양도를 통하여 프로세스는 일시적으로 추첨권을 다른 프로세스에게 넘겨줄 수 있다.

(3) 추첨권 팽창
: 프로세스는 일시적으로 자신이 소유한 추첨권의 수를 늘이거나 줄일 수 있다. 물론 서로 신뢰하지 않는 프로세스들이 상호 경쟁하는 시나리오에서는 의미가 없다. 

## 2. 구현
추첨 스케줄링의 가장 큰 장점은 구현이 단순하다는 것이다.

난수 발생기 , 프로세스들의 집합을 표현하는 자료 구조, 추첨권의 전체 개수 뿐

-> 각 사용자에게 추첨권을 나누어 준 후 사용자가 알아서 실행시키고자 하는 작업들에게 추첨권을 배분하는 것이다.

-> 해결책은 여전히 추첨권 할당 문제에 대해서는 여전히 미해결이다.

## 3. 왜 결정론적 방법을 사용하지 않는가
무작위성을 이용하면 짧은 기간만 실행되는 경우일 수록 정확한 비율을 보장할 수 없다.

-> 이 때문에 결정론적 공정 배분 스케줄러인 보폭 스케줄링을 만들었다.

보폭은 자신이 가지고 있는 추첨권 수에 반비례하는 값이다. 

보폭 스케줄링은 각 스케줄링 주기마다 정확한 비율로 CPU를 배분한다.


### 추첨 스케줄링은 상태 정보가 필요 없다. 
