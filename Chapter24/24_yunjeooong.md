# 24장. 메모리 가상화 핵심 정리

- 프로세스는 **명령어를 가져오고**, **명확한 Load/Store 방식**으로 메모리에 접근한다.
- 프로그램이 다루는 주소는 **물리 주소가 아닌 가상 주소**이다.
- 이로 인해, 프로그램은 **실제 메모리에 모든 데이터와 코드가 존재하는 것처럼 동작**한다.
- **TLB(변환 조회 버퍼)**는 주소 변환을 빠르게 하기 위해 설계된 **소형 하드웨어 캐시**이다.
- TLB 덕분에 **가상 주소를 물리 주소로 신속히 변환**할 수 있다.
- **페이지 테이블**은 방대한 크기로 인해 **느린 메모리 공간**에 저장된다.
- 초기의 페이지 테이블은 단순한 **배열 형태**였으나, 이후 **다단계 구조**로 발전해 효율을 높였다.
- 주소 변환 체계는 **필요한 경우에만 메모리 공간을 동적으로 할당**할 수 있어야 한다.
    - 예: **다단계 페이지 테이블**을 활용한 유연한 메모리 할당.
- **페이지 교체 정책**은 제한된 물리 메모리를 효율적으로 사용하기 위해 필요하다.