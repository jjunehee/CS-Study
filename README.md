# CS-Study


## 2023-07-10

정규성
<details>
 <summary> OSI7계층과 그 존재 이유, TCP/IP 4계층에 대해 설명해보세요. </summary>
</br>
    
   OIS7계층은 네트워크 통신이 일어나는 과정을 7단계로 나눈것이다. 이렇게 하면 통신이 일어나는 과정을 단계별로 파악할 수 있으며, 문제가 발생할 경우 해당 부분만을 고쳐서 해결할 수 있다. 다만 실제로 구현한 예는 거의 없다.
    
   1. 물리계층 : 신호로 변환하여 전송하는 계층 (허브, 케이블)
   2. 데이터 링크 계층 : 패킷 데이터를 실어 보내는 계층 (스위치, 브릿지)
   3. 네트워크 계층 : 네트워크를 논리적으로 구분하고 연결하는 계층(라우터 + 라우팅 프로토콜)
   4. 전송  계층 : 서비스를 구분하고 데이터의 전송 방식을 담당하는 계층(TCP, UDP)
   5. 세션 계층 : 응용 프로그램 간의 연결을 지원해주는 계층
   6. 표현 계층 : 데이터의 변환 작업을 하는 계층(데이터 암호화, 복호화)
   7. 응용 계층 : User Interface 를 제공하는 계층(chrome, discord, 한글)
    
  그에 비해 TCP/IP 4계층은 실질적인 네트워크 통신에 사용된다. 7계층의 1, 2 가 하나로 통합되고, 5, 6, 7 이 하나로 통합된다. 
    
   1. Network Access Layer : 네트워크 카드와 디바이스 드라이버 등과 같이 하드웨어적인 요소와 관련되 는 모든 것을 지원하는 계층(CSMA/CD, MAC, LAN + Ehternet(이더넷), Token Ring, PPP)
   2. Internet Layer : 상위 트랜스포트 계층으로부터 받은 데이터에 IP패킷 헤더를 붙여 IP패킷을 만들고 이를 전송하는 계층(IP, ARP, RARP)
   3. Transport Layer : 네트워크 양단의 송수신 호스트 사이에서 신뢰성 있는 전송기능을 제공(TCP, UDP)
   4. Application Layer : 응용프로그램들이 네트워크서비스, 메일서비스, 웹서비스 등을 할 수 있도록 표준적인 인터페이스를 제공(HTTP, FTP, Telnet, DNS, SMTP)

    
   </p>
</details>

<details>
 <summary> 프로세스 동기화에 대해 설명해보세요. </summary>
 <div markdown="1">
  </br>
  두 개 이상의 프로세스가 동일한 자원에 접근하면 데이터의 일관성을 해칠 수 있다.
    
   이런 상황을 경쟁상황(race condition)이라고 부른다.
    
   이런 상황을 유발할 수 있는 코드를 임계 구역(Critical Section)이라고 부른다.
    
   이를 해결하기 위해서는 3가지 조건을 만족해야한다.
    
   1.  Mutual Exclusion (상호 배제)
        
        이미 한 프로세스가 Critical Section에서 작업 중이면 다른 모든 프로세스는 Critical Section에 진입하면 안 된다.
        
   2. Progress (진행)
        
        Critical Section에서 작업 중인 프로세스가 없다면, Critical Section에 진입하고자 하는 프로세스가 존재하는 경우 진입할 수 있어야 한다.
        
   3. Bounded Waiting (한정 대기)
        
        프로세스가 Critical Section에 들어가기 위해 요청한 후부터, 그 요청이 허용될 때까지 다른 프로세스들이 Critical Section에 들어가는 횟수에 한계가 있어야 한다. 쉽게 말해, Critical Section에 진입하려는 프로세스가 무한정 기다려서는 안 된다. 
        
        ⇒ 모종의 이유로 아무도 사용하지 않는 자원을 무한정 기다려서는 안된다.
</details>
   
<details>
 <summary> RDBMS vs NOSQL에 대해서 설명해주세요. </summary>
 </br>
 <div markdown="1">
  <p>RDBMS 는 정해진 스키마에 따라 데이터를 저장하고 구성된 테이블이 다른 테이블과 관계를 맺는다. 이를 위해 외래키를 사용하며, 이를 통해 테이블을 통합하여 데이터를 얻을 수 있다. 데이터 구조화하여 정의하기 편하다. 성능향상을 위해서 서버의 처리 능력 향상이 필요하다. scale up</p>

    
   <p>NOSQL 은 테이블 간의 관계를 정의하지 않고 저장한다. 데이터의 일관성을 포기하고 빅데이터 트래픽 처리에 장점을 가진다. 성능향상을 위해서 분산처리를 지원한다. scale out(수평 확장)</p>
</details>
   
조준희
<details>
 <summary> RESTful이란 무엇이며, 이것에 대해서 아는대로 설명해보세요.(보충필요) </summary>
 <div markdown="1">
</details>

<details>
 <summary> 프로세스와 스레드의 차이를 설명해보세요. </summary>
 <div markdown="1">
</details>
   
<details>
 <summary> ACID에 대해서 설명해주세요. </summary>
 <div markdown="1">
</details>
