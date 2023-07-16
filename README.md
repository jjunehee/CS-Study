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

  REST의 원리를 잘 따르는 시스템, 그중에서도 REST API 설계 규칙을 올바르게 따르는 시스템을 Restful하다고 할 수 있다.
  
  이때 REST란,
  1. HTTP URI 를 통해 자원을 명시하고
  2. HTTP Method(GET, POST, PUT, DELETE) 를 통해
  3. 해당 자원에 대한 CRUD(생성, 조회, 수정, 삭제)를 적용하는 것을 의미한다.

  라고 보통 알고있는데, "REST란 HTTP 를 잘 사용하기 위한 아키텍쳐 스타일"이 더 알맞다.

  REST의 특징으로는,
  1. Client-Server
     - API를 통해 정보를 교환하는 주체는, 클라이언트와 서버 구조를 가져야한다.
     - 클라이언트와 서버를 분리함으로써, 서로 의존하지 않는 구조를 가져야한다.
  2. Stateless
     - 무상태성 (서로의 상태를 기억하지 않는다.)
     - 클라이언트에서 서버로의 요청에는 그 요청을 이해하는 데 필요한 모든 정보가 포함되어있어야한다.
  3. Cache
     - cache-control header를 통해 요청에 대한 응답 내의 데이터에 캐시 가능여부가 명시되어 있어야한다.
  4. Uniform Interface (.....? 이해가 안간다.. 이건...)
     - 전체 시스템을 파악할 수 있는 인터페이스를 제공해야한다.
  5. Layered System
     - 계층화 시스템
     - 클라이언트는 서버에 직접 연결되었는지, 중간 서버를 통해 연결되었는지 알 수 없어야함을 의미합니다.
     
  또한 REST API란, REST 한 방식으로 데이터를 상호교환 하도록 설계된 API를 의미하고, 이를 올바르게 설계하기 위한 규칙이 존재한다.
  1. URI는 동사보다 명사를, 대문자보다는 소문자를 사용해야한다.
  2. 마지막에 슬래시(/)를 사용해서는 안된다.
  3. 언더바 대신, 하이픈(-)을 사용한다.
  4. 파일확장자는 URI에 포함하지 않는다.
  
</details>

<details>
 <summary> 프로세스와 스레드의 차이를 설명해보세요. </summary>
 <div markdown="1">
  프로세스는 메모리 상에서 실행중인 프로그램을 말하며, 스레드는 이 프로세스 안에서 실행되는 흐름 단위를 말한다.
  
  프로세스는 각각 독립된 메모리 영역(Code, Data, Stack, Heap)을 할당받는다. 각 프로세스는 별도의 주소 공간에서 실행되며, 한 프로세스는 다른 프로세스의 변수나 자료구조에 접근할 수 없다. 한 프로세스가 다른 프로세스의 자원에 접근하려면 프로세스 간의 통신(IPC)를 사용해야 한다.
  
  이에 반해 스레드는 한 프로세스 내에서 각각 Stack만 따로 할당받고, Code, Data, Heap 영역에서 서로 자원을 공유하고 접근할 수 있다. 따라서 프로세스간 통신이 불가해서 오는 컨텍스트 스위칭 비용, 프로세스간 통신(IPC)비용을 줄일 수 있는 이점이 있다. 하지만 스레드 간의 자원 공유는 동기화 문제가 발생할 수 있다는 특징이 있다.

+ 추가 질문 ( 컨텍스트 스위칭, IPC에 대해 설명해봐라, 메모리 영역(Code, Data, Stack, Heap)에 대해 설명해봐라, 동기화 문제는 무엇이고 어떻게 해결해야하는가?)
</details>
   
<details>
 <summary> ACID에 대해서 설명해주세요. </summary>
 <div markdown="1">

  Atomicity 원자성
  - 하나의 트랜잭션에 속한 모든 작업이 "전부 성공하거나 전부 실패"하는 것을 보장한다.

  Consistency 일관성
  - 트랜잭션이 성공적으로 끝나면 데이터베이스의 제약/규칙과 같은 상태는 언제나 이전과 같고 유효해야한다.

  Isolation 독립성
  - 트랜잭션은 다른 트랜잭션의 연산에 영향을 끼치지 못하는 것을 보장한다.
  - 모든 트랜잭션은 다른 트랜잭션으로부터 독립 되어야한다.

  Durabilty 지속성
  - 성공적으로 수행된 트랜잭션은 영원히 반영되어야 한다.
</details>


## 2023-07-11

정규성
<details>
 <summary> apache 와 nginx, tomcat 의 역할과 차이점 </summary>
</br>
    apache는 웹 서버의 역할을 합니다. 멀티 프로세스 방식으로 동작하며 안정성에 장점이 있습니다. 다만 모든 연결에 프로세스를 할당하다보니 성능이 비교적 떨어집니다.

nginx는 마찬가지로 웹 서버의 역할을 하지만, 이벤트 기반 방식으로 동작합니다. 여기서 이벤트 기반 방식이란, 연결 요청이 nginx 가 가진 큐에 차례로 들어있다가 하나씩 요청을 스레드를 할당해 처리합니다. 이때 연결에서 별다른 요청이 없다면 다른 연결의 요청을 처리하는 방식입니다. 이를 통해 가볍고 성능이 비교적 좋습니다.

tomcat은 웹 어플리케이션 서버의 역할을 합니다. JAVA로 작성된 프로그램으로, http 요청을 받고 동적인 페이지를 만들어 제공하는 것이 목적으로 합니다. 웹 서버와 같이 연동해서 사용하면 성능을 향상시킬 수 있습니다.
   
</details>

<details>
 <summary> 컨텍스트 스위칭에 대해 설명해보세요. </summary>
</br>
   컨텍스트 스위칭은 여러개의 프로그램이 동시에 실행되는 경우 프로세스의 처리를 빠르게 바꿔가며 하기 위해 필요한 기술입니다.

이를 위해, 한 프로세스로 부터 CPU자원을 프로세스로 넘겨줍니다. cpu가 프로세스를 동작시킬 때 필요한 정보를 context라고 하며, 이 정보가 PCB에 저장됩니다. A프로세스가 실행중에 스케쥴러에 의해 B 프로세스의 실행을 요청하면 A의 정보를 PCB에 저장하고, B의 정보를 PCB로 부터 불러와서 작업을 진행합니다. 이럼

이때 어떤 프로세스를 요청할 지 여부를 결정하는 스케쥴링 방식에 따라 성능이 달라질 수 있으며, 이 과정이 과도하게 일어날 경우 오버헤드가 발생하며 오히려 성능이 저하될 수 있다.
   
</details>

<details>
 <summary> 데이터베이스에서 인덱스를 사용하는 이유 및 장단점에 대해 설명해주세요. </summary>
</br>
   데이터베이스에서 인덱스를 사용하는 이유는 테이블에 대한 동작의 속도를 높이기 위해서입니다. 인덱스를 key-value 구조로 이루어지며, 특정 컬럼에 인덱스를 생성하면, 해당 컬럼의 데이터를 정렬하여 별도의 메모리 공간에 실제 메모리 주소와 함께 저장한다. 이를 구현하기 위해 여러 방법이 있지만, 주로 B+Tree 구조를 사용한다. B+tree 의 경우 balanced-tree 구조로 설계되어 수직탐색에 유리하며, leaf 노드에만 데이터를 저장하고 이를 linked-list로 연결하여 수평탐색에도 유리하다.
   
</details>

조준희
<details>
 <summary> TCP와 UDP의 차이점에 대해서 설명해보세요. </summary>
</br>
 TCP는 데이터의 신뢰성을 보장하는 연결 지향적 프로토콜이다.
 데이터의 손실이 없고, 순서대로 전달된다는 특징을 가지고 있다.
 TCP는 데이터를 전송하기 전에 송수신 기기간 논리적 연결을 하고, 이를 가상 회선이라고 한다.
 이렇게 생성된 회선을 통해 송신자는 패킷 전송이 잘 되었는지 확인하는 과정과 흐름제어 혼잡 제어와 같은 과정을 거치면서 패킷의 순서와 손실을 방지하면서 데이터 전송이 가능하게 해준다.

 UDP는 데이터의 신뢰성 보다는 전송 속도를 위한 비연결 지향적 프로토콜이다.
 데이터의 손실 가능성이 있어 데이터의 신뢰성은 보장할 수 없지만, 빠르게 데이터를 전송할 수 있다는 특징을 가지고 있다.
 UDP는 TCP와 다르게 가상회선 방식과 같이 연결을 설정하지 않고, 독집적인 데이터그램 형태로 패킷마다 각각 다른 경로로 수신자에게 보내지게된다. 이 때문에 데이터의 순서가 보장되지 못하며, 패킷이 잘 도착했는지 또는 흐름 제어와 혼잡 제어같은 기능을 처리하지 않기 때문에 데이터의 손실이 발생할 수 있다. 하지만 이로인해 네트워크 부하가 적어서 TCP보다 전송 속도가 빠르다.
</details>

<details>
 <summary> 동기와 비동기의 차이(블로킹, 넌블로킹) / 장단점에 대해 설명해보세요. </summary>
</br>
동기방식 : 호출된 함수의 수행 결과 및 종료를 호출한 함수가 신경쓰는 방식

비동기 방식 : 호출된 함수의 수행 결과 및 종료를 호출한 함수가 신경쓰지 않는 방식

블로킹 : 호출된 함수가 자신이 할 일을 모두 마칠 때까지 제어권을 계속 가지고서 호출한 함수에게 바로 return하지 않는 방식

논-블로킹 : 호출된 함수가 자신이 할 일을 마치지 않았더라도 바로 제어권을 바로 return 하여 호출한 함수가 다른 일을 진행할 수 있도록 하는 방식

동기 & 블로킹, 비동기 & 블로킹 : 결국 호출된 함수가 끝날 때를 기다려야 하기 때문에 동기, 비동기에 상관없이 블로킹이라면 비슷한 효율을 가진다.

동기 & 논-블로킹 : 호출된 함수로부터 제어권을 바로 return 받아서 다른 작업을 수행할 수는 있지만 다른 작업을 하면서도 동기방식이기 때문에 호출된 함수의 결과를 계속 신경 쓰게 된다. 이로 인해 작업의 효율이 좋지 못하다.

비동기 & 논-블로킹 : 호출된 함수의 결과를 기다리지도 않으며 자신의 작업을 계속 수행하고, 콜백을 통해 호출된 함수의 결과를 받는다. 그렇기 때문에 자원이 충분하다면 효율이 좋은 방식이다.
   
</details>

<details>
 <summary> 정규화에 대해서 설명해주세요. </summary>
</br>
정규화의 기본 목표는 테이블 간에 중복된 데이터를 허용하지 않는 것으로, 중복된 데이터를 허용하지 않음으로써 무결성을 유지할 수 있으며, DB간의 저장 용량 역시 줄일 수 있는 방법이다.

따라서 테이블을 분해하는 여러 단계로 정의된다.

[제1정규화]
테이블의 칼럼이 원자값(하나의 값)을 갖도록 테이블을 분해한다.

[제2정규화]
테이블의 기본키의 부분집합이 결정자가 되어서는 안된다.
ex) 복합키 (A,B)가 기본키로 된 테이블에서 B만으로도 C가 달라지는 상황이 발생하면, 
B가 결정자가 되므로 이는 제2정규화의 대상이 된다.

[제3정규화]
테이블에 대해 이행적 종속을 없앤다.
여기서 이행적 종속이란 A -> B, B -> C 가 성립할 때, A-> C가 성립되는 상황을 의미한다.

[BCNF 정규화]
테이블에 대해 모든 결정자가 후보키가 되도록 테이블을 분해하는 것이다.
   
</details>



## 2023-07-12

정규성
<details>
 <summary> HTTP와 HTTPS의 차이점에 대해서 설명해보세요. </summary>
</br>
 http는 어플리케이션 레이어에서 동작하는 프로토콜입니다. 요청과 응답으로 구성됩니다. 브라우저 사용자가 웹 서버에 http get 요청을 보내면 웹 서버는 요청을 받고 이에 해당하는 암호화되지 않은 데이터를 응답합니다.

https 는 http연결에 보안을 추가한 프로토콜입니다. ssl 혹은 tsl 기술을 활용하여 암호화를 진행하여 중간에 데이터를 확인할 수 없습니다. 이를 구축하기 위해서는 외부 인증 기관에서 ssl 혹은 tsl 인증서를 획득하고 이를 공유해야합니다.  

++SSL? TSL?

ssl 과 tsl 은 모두 시스템 간의 암호화를 제공합니다. tsl 은 ssl 의 업데이트 버전이며, ssl 은 3.0 버전 이후로 업데이트 되지 않으며, tsl 1.0으로 업데이트를 진행중입니다.

tsl 이 되면서 ssl 에 비해 핸드셰이크 프로세스가 짧아지고 암호화 과정을 줄여 프로세스 속도가 올라갔습니다.
</details>

<details>
 <summary> Spring Bean이란 무엇인가요? </summary>
</br>
 spring은 제어의 역전이 일어나므로, 일부 자바 객체를 관리합니다. 이때 관리되는 자바 객체들을 bean 이라고 부릅니다. 

bean에 객체를 등록하기 위한 방법은 여러가지가 있습니다.

1. xml 파일에 bean 태그를 활용하여 등록 : xml 파일에 bean 태그와 함께 class 의 경로와 property를 입력하면 bean에 등록할 수 있습니다. 
2. component scan : 특정 annotation 을 붙이면 spring이 이를 읽고, 자동으로 bean 객체를 만들어 줍니다.(component, controller, service, repository, configuration …)
    
    이후 xml 파일에 component-scan context 를 통해 annotation이 달린 객체들을 bean으로 만듭니다. ⇒ 이 과정은 ComponentScan annotation 으로 대체될 수 있습니다.
    
3. @Bean annotation 활용 : configuration annotation 과 함께 bean annotation 으로 객체를 return 하는 메소드를 bean으로 등록할 수 있습니다.
</details>

<details>
 <summary> TDD를 알고 있나요? TDD에 대해서 어떻게 생각하나요? </summary>
</br>
 TDD란 테스트 주도 개발으로, 개발을 마치고 테스트를 진행하는 것이 아니라, 테스트를 먼저 준비하고 이에 맞춰 개발을 진행하는 개발 방법을 말합니다. 

장점

1. 설계 수정 시간의 단축 : 테스트 코드를 먼저 작성하기 때문에 입출력 데이터와 기능을 명확하게 하므로 문제를 사전에 발견할 수 있습니다.
2. 유지 보수 용이성 : 기본적으로 단위 테스트를 위한 테스트 코드를 작성하기 때문에, 추후에 모듈 별로 테스트를 진행하면서 유지 보수가 용이해집니다.
3. 테스트 문서 작성 보조 : TDD 를 진행하며 테스트를 자동화시킴과 동시에 더 정확한 테스트 근거로 테스트 문서를 보완할 수 있습니다.

단점

1. 사전 준비 기간 : 프로젝트 도입시 사전에 지식을 습득하고 개발 환경 구축하는 데에 많은 시간이 걸린다. TDD 를 효과적으로 사용할 수 있는 수준의 교육에는 수준에 따라 1~6개월이 걸립니다.
2. 생산성 저하 : 개발 기간이 짧은 경우 TDD 를 이용해 테스트 코드를 작성하고 이를 통과하기 위한 코드를 작성한다면 개발 기간이 그만큼 더 부족해 질 수 있습니다.
</details>

조준희
<details>
 <summary> 프로세스 동기화란? </summary>
</br>
 하나의 자원을 한 순간에 하나의 프로세스만이 이용하도록 제어하는 것.

 여러 프로세스들이 동시에 자원에 접근하는 상황에서 실행 순서에 따라 결과값이 달라질 수 있는데, 이 상황을 경쟁 상태(Race Condition)이라고 한다. 이런 경쟁 상태가 발생하면 자원의 일관성이 깨질 수 있는 문제가 발생한다. 그리고 이 동일한 자원에 접근하는 코드 부분을 Critical Section(임계구역)이라고 한다.

 이런 문제를 해결하기 위한 3가지 방법이 존재한다.
 1. Mutual Exclution(상호 배제)
    - 이미 한 프로세스가 Critical Section(임계 구역)에서 작업 중이면 다른 모든 프로세스는 임계구역에 진입해서는 안된다.
 2. Progress(진행)
    - 임계구역에서 작업 중인 프로세스가 없다면, 임계구역에 진입하고자 하는 프로세스가 존재하는 경우 진입할 수 있어야 한다.
 3. Bounded Waiting(한정 대기)
    - 프로세스가 임계구역에 들어가기 위해 요청한 후부터 그 요청이 허용될 때까지 다른 프로세스들이 임계구역에 들어가는 횟수에 한계가 있어야 한다. 즉, 임계구역에 진입하려고 프로세스가 무한정 기다려서는 안된다.
</details>

<details>
 <summary> 멀티스레드 프로그래밍에 대해 설명해보세요. </summary>
</br>

 하나의 프로세스들이 다수의 실행 단위로 구분하여 자원을 공유하고 자원의 생성과 관리의 중복성을 최소화하여 수행 능력을 향상시키는 것을 의미한다. 즉, 하나의 프로그램에 동시에 여러개의 일을 수행할 수 있도록 해주는 것이다.
 프로세스를 이용하여 처리하던 일을 쓰레드로 처리할 경우 메모리 공간과 시스템 자원 소모가 줄어들게 된다. 또한 스레드 간의 통신이 필요한 경우에도 스레드간에는 데이터와 힙(Heap)영역을 공유하기 때문에 프로세스 간 통신 방법(IPC)에 비해 훨씬 간단하다. 하지만 멀티 쓰레딩 환경에서는 공유하는 영역이 있기 때문에 공유하는 자원에 대해 동기화 작업이 필요하다.
</details>

<details>
 <summary> RDBMS vs NOSQL에 대해서 설명해주세요. </summary>

 RDBMS
 - 관계형 데이터베이스를 의미한다.
 - 테이블 간의 정보가 서로 관계성을 가지고 있는 것이 특징이고, 2차원 행렬로 테이블을 표현하는 데이터베이스이다. 이러한 관계를 통해 테이블 간 join이 가능하다.
 - 정해진 스키마에 따라 데이터를 저장해야 하므로 명확한 데이터 구조를 보장받을 수 있다.
 - 하지만 이런 정해진 스키마로 인해 스키마가 자주 바뀌는 환경에서는 번거로울 수 있다.
 - ACID 원칙을 기본으로 구성된 방식으로 정확한 데이터 처리가 가능하다.

<br>

 NoSQL
 - Not Only SQL의 약자로, 테이블 간 상호관계가 없는 것이 특징이다. 관계가 없으므로 다른 테이블과 join도 할 수 없다.
 - 많은 양의 데이터를 저장, 처리할 수 있다.
 - RDBMS와 다르게 스키마가 정해져 있지 않아 구조 변경이 용이하고 데이터 형식이 다양하며 바꾸기 쉽다.
 - 스키마가 존재하지 않아서, 데이터의 일관성이 존재하지 않는다. 이로 인해 데이터 중복이 발생할 수 있어서 데이터가 변경될 경우 모든 컬렉션에서 update해야하는 번거로움이 있다.
 - ACID를 보장하지 않는 경우가 있어서, 정확한 데이터 처리보다는 대용량 데이터 처리에 용이하다.
</br>
</details>

## 2023-07-13

정규성
<details>
 <summary> HTTPS에 대해서 설명하고 SSL Handshake에 대해서 설명해보세요. </summary>
</br>
 https 는 http에 보안 절차를 추가한 과정입니다. 이 과정에 SSL/TLS 기술이 추가됩니다. 

SSL 을 활용한 인증을 위해 SSL 핸드셰이크를 진행합니다.

SSL 핸드셰이크과정

1. client hello : 브라우저가 사용하는 SSL 버전과 암호화 방식, 난수를 포함하여 웹 서버에 접속합니다.
2. 웹 서버는 서버 암호화 방식, 서버 공개키, 난수를 포함하여 응답합니다.
3. 브라우저는 자체 내장 공개키를 활용해 서버의 SSL 인증이 유효한지 확인합니다. 
4. 브라우저는 자신의 난수와 서버에서 받은 난수로 데이터를 만들고 이를 공개키로 암호화하여 웹 서버로 보냅니다.
5. 서버는 이를 복호화하여 세션키를 생성합니다. 세션키는 이후 대칭키 암호화에 사용됩니다.
6. 이제 세션키를 활용하여 암호화, 복호화를 진행하며 https 통신을 진행합니다. 이후 통신이 종료되면 세션키를 폐기합니다.
</details>

<details>
 <summary> 프로세스와 스레드의 차이를 설명해보세요. </summary>
</br>
 프로세스는 OS 에서 메모리에 올라와 실행되는 프로그램입니다. CPU를 점유하며, code/data/stack/heap 의 구조로 독립적 메모리를 가집니다.

스레드는 프로세스 내에서 실행되는 작업입니다. 스레드는 프로세스 내에서 stack 을 독립적으로 가지며, code/data/heap 을 공유합니다.

++ 프로세스 통신과 스레드 통신방법의 차이를 말해보세요

프로세스 간 통신에는 파이프, 파일, 소켓 등의 통신 방법을 이용해서 데이터를 주고 받을 수 있습니다.

스레드 간에는 메모리 영역을 공유하기 때문에 별다른 통신과정없이 데이터를 공유할 수 있습니다.

++ 멀티 프로세스와 멀티 스레드의 차이에 대해 말해보세요

멀티 프로세스는 한 프로그램이 여러 개의 프로세스로 구성되는 구조입니다. 각 작업이 나눠져 있기 때문에 한 프로세스에 문제가 생겨도 다른 프로세스에 직접적으로 문제가 발생하지 않습니다. 다만 각 프로세스가 한 처리 단위이기 때문에 context switching 이 발생하며 이 과정에서 오버헤드가 발생할 수 있습니다.

멀티 스레드는 한 프로그램이 여러개의 스레드로 구성되는 구조입니다. 프로세스 할당에 자원이 사용되지 않으므로 자원을 효율적으로 사용합니다. 다만 한 프로세스에서 다른 프로세스의 스레드를 제어할 수는 없기 때문에 결국 프로세스 간 통신이 필요하며, 자원을 공유하기 때문에 동기화 문제가 발생할 수 있습니다.
</details>

<details>
 <summary> Checked Exception과 Unchecked Exception에 대해 설명해주세요. 스프링 트랜잭션 추상화에서 rollback 대상은 무엇일까요? </summary>
</br>
 checked exception 은 java 에서 반드시 try-catch 문으로 묶어서 예외 처리가 필요한 exception 입니다. unchecked exception 은 runtimeException 을 상속받는 exception 입니다.

스프링 트랜젝션을 추상화 했다면 별도의 commit, rollback 시점을 지정하지 않았기 때문에, uncheckedException이 발생했다면 rollback, checkedException 이 발생했다면 rollback하지 않습니다.

++ 스프링 트랜잭션 추상화에 대해 설명해보세요

DB와의 connection을 통해 직접 트랜젝션을 수행한다면 JDBC, JPA 등특정 구현기술에 종속됩니다. 이를 방지하기 위해 트랜잭션 관리자를 사용합니다. 트랜잭션 관리자라 connection 을 담당하면 사용자는 connection 과 상관 없이 같은 서비스 코드로 요청을 보내면 됩니다.
</details>

조준희
<details>
 <summary> Spring DI/IoC에 대해 설명해시오 </summary>
</br>
IoC는 "제어의 역전" 이라는 의미로, 객체나 메서드의 호출을 개발자가 결정하는 것이 아닌, 객체의 생성에서부터 생명주기의 관리까지 모든 객체에 대한 제어권을 프레임워크 내부에서 결정한다는 의미이다.

DI "의존성 주입" 은 스프링 프레임워크에서 지원하는 IoC의 한 형태로 클래스 사이의 의존관계를 빈 설정 정보를 바탕으로 컨테이너가 자동으로 연결해줍니다.
의존성 주입의 방법으로슨 생성자 주입, setter 주입, 필드 주입이 있다.

스프링에서는 스프링 컨테이너(Application Context)를 이용하여 설정 정보를 생성, 등록하고 필요한 객체를 생성자, setter, 필드를 통해 주입합니다.
 
</details>

<details>
 <summary> Spring Bean이란 무엇인가요? </summary>
</br>
우리가 알던 기존의 Java Programming 에서는 Class를 생성하고 new를 입력하여 원하는 객체를 직접 생성한 후에 사용했었습니다. 하지만 Spring에서는 직접 new를 이용하여 생성한 객체가 아니라, Spring에 의하여 관리당하는 자바 객체를 사용합니다. 이렇게 Spring에 의하여 생성되고 관리되는 자바 객체를 Bean이라고 합니다. Spring Framework 에서는 Spring Bean 을 얻기 위하여 ApplicationContext.getBean() 와 같은 메소드를 사용하여 Spring 에서 직접 자바 객체를 얻어서 사용합니다.

Bean 생성은 @component, @Controller, @Service, @Repository과 같은 어노테이션으로 등록이 가능하며,  Bean Configuration File에 직접 Bean 등록하는 방법이 있습니다.
</details>

<details>
 <summary> Servlet Filter와 Spring Interceptor의 차이는 무엇인가요? </summary>
</br>
 필터는 말 그대로 요청과 응답을 거른뒤 정제하는 역할을 한다.
Dispatcher Servlet에 요청이 전달되기 전 / 후에 url 패턴에 맞는 모든 요청에 대해 부가 작업을 처리할 수 있는 기능을 제공한다.
즉, 스프링 컨테이너가 아닌 톰캣과 같은 웹 컨테이너에 의해 관리가 되는 것이고, 스프링 범위 밖에서 처리되는 것이다.
 보안 및 인증/인가 관련 작업, 모든 요청에 대한 로깅 또는 검사, 데이터 압축 및 문자열 인코딩, Spring과 분리되어야 하는 기능에 사용된다.

 인터셉터는 요청에 대한 작업 전 / 후로 가로챈다고 보면 된다.
Dispatcher Servlet이 Controller를 호출하기 전 / 후에 인터셉터가 끼어들어 요청과 응답을 참조하거나 가공할 수 있는 기능을 제공한다.
웹 컨테이너에서 동작하는 필터와 달리 인터셉터는 스프링 컨텍스트에서 동작한다.
세부적인 보안 및 인증/인가 공통 작업, API 호출에 대한 로깅 또는 검사, Controller로 넘겨주는 정보(데이터)의 가공에 사용된다.
</details>

## 2023-07-14

정규성
<details>
 <summary> http 1 과 http 2 의 차이에 대해 설명해보세요 </summary>
</br>
 지나치게 많은 내용이 있기 때문에 일부만 간추려서 설명합니다.

- http 1.0
    
    하나의 connection 은 하나의 요청만을 처리합니다. 하나의 요청과 응답이 끝나면 연결을 종료합니다. 이 연결과정에서 긴 과정이 걸립니다.
    
- http 1.1
    
    한 번 connection 을 연결하면, 이 세션이 유지되는 동안 요청과 응답을 주고받을 수 있습니다. 다만 동시에 하나의 요청만을 처리할 수 있습니다. 따라서 여러개의 리소스를 요청하는 데에 결리는 시간도 길어집니다.
    
    이 과정에서 하나의 패킷의 처리에 시간이 걸리면, 이후의 모든 요청이 막히게 됩니다. 이를 HOL(head-of-line) blocking 이라고 합니다.
    
    요청에 대한 응답을 받지 않아도 계속 요청을 보낼 수 있습니다. 이를 pipelining 이라고 합니다. 다만, 요청에 대한 응답이 순서대로 오리라는 보장이 없다는 문제가 있습니다.
    
    여러개의 요청에 대해 여러개의 connection 을 만들어서 동시에 응답을 받아올 수 있습니다. 이를 Domain sharding 이라고 합니다. 다만 많은 conneciton에 따른 트래픽이 발생합니다.
    
- http 2
    
    앞서 1.1 버전에서 발생한 리소스 요청에 관한 부분들을 해결하기 위해 한 개의 connection 으로 동시에 여러개의 데이터를 주고 받을 수 있으며 응답의 순서로 상관없습니다. 이를 multiplexed stream 이라 합니다. 
    
    http 통신과정에 유용하게 사용되는 header 는 때때로 과도한데, 이를 압축하여 보낼 수 있습니다.
    
    하나의 요청에 포함된 다른 요청들을 동시에 처리하여 응답합니다. 따라서 요청을 여러반 반복할 필요가 없습니다.
    
    여러개의 요청에 우선순위를 부여하여 응답할 수 있습니다. 
    
    보안 통신을 지원합니다. http요청과 SSL/TLS 를 활용해 요청을 암호화합니다.
</details>

<details>
 <summary> 가상 메모리에 대해 설명해보세요. </summary>
</br>
 초창기 컴퓨터는 프로그램을 실행시키기 위해 RAM 에 프로그램의 모든 주소공간이 들어가야 했습니다. 이를 해결하기 위해 가상 메모리 기법이 등장했습니다. 

프로그램을 실행하면 실행에 필요한 일부분 만을 메모리에 올립니다. 이렇게 올라간 주소와 실제 디스크의 위치를 매칭시키는 작업을 MMU가 담당합니다. cpu는 MMU를 통해 디스크에 위치한 실제 프로그램을 찾아 실행합니다.

이때 모든 주소를 메핑하는 것은 비효율적이므로 일부분을 한 블록으로 묶어 관리한다. 이때 일정한 단위로 묶는다면 페이징, 필요에 따라 다른 크기로 묶는 것은 세그멘테이션이라고 합니다. 혹은 이를 합쳐서 세그먼트를 페이징 하는 방법이 있습니다.

이렇게 나뉜 페이지를 실제 메모리로 가져와서 작업합니다.

이렇게 올라간 데이터는 cpu가 호출할 때 가상메모리에는 올라갔지만 RAM에 올라가지 않은 경우가 있는데, 이때 자동으로 해당 부분을 RAM으로 호출하고 다시 같은 명령을 수행하는 것은 page faults 라고 합니다.

따라서 어떤 페이지를 메모리에 유지할 지 결정하는 것이 중요합니다.
</details>

<details>
 <summary> 정규화에 대해서 설명해주세요. </summary>
</br>
 정규화는 DB구조를 변경하여 이상현상을 제거하는 작업입니다. 

이상현상이란 

1. 삽입 이상 : 자료를 삽입할 때 의도하지 않는 자료까지 삽입해야하는 현상
2. 갱신 이상 : 중복된 데이터 중 일부만 수정되어 모순이 일어나는 현상
3. 삭제 이상 : 어떤 정보를 삭제하면 의도하지 않는 다른 정보까지 삭제되는 현상

이 있습니다.

제1 정규형

- 컬럼이 원자값을 갖도록 합니다. 즉, 하나의 컬럼은 하나의 값 만을 가지도록 합니다.

제2 정규형

- 완전 함수 종속을 만족하도록 테이블을 분리해야합니다. 즉, 기본키의 부분집합에 의해 결정되는 컬럼이 있어서는 안됩니다.

제3 정규형

- 이행 종속성을 없어야 합니다. 즉, A가 B를 결정하고, B가 C를 결정하는데, A가 C를 결정할 수 있는 상황을 이행 종속이라고 합니다.

BCNF

- 모든 결정자가 후보키에 속해야합니다. 즉, 후보키 집합에 없는 컬럼이 결정자가 되어서는 안됩니다.

제4 정규형

- 다치 종속이 없어야 합니다. 즉, A→B 일때, A에 해당하는 B의 값이 여러개인 경우, 이런 컬럼이 여러개가 되는 경우 테이블을 분리해야합니다.

제5 정규형

- 조인 종속이 없어야 합니다. 즉, 하나의 릴레이션을 여러 개의 릴레이션으로 무손실 분해했다가 다시 결합할 수 있다면 5 정규형을 만족합니다.
</details>

조준희
<details>
 <summary> HTTP와 HTTPS의 차이점에 대해서 설명해보세요.</summary>
</br>
- HTTP와 HTTPS의 가장 큰 차이는 보안이다. HTTP의 문제점은 서버에서부터 전달되는 데이터가 암호화가 되지 않은 평문이기ㅎㅎ 때문에, 제 3자가 중간에 개입하여 정보를 탈취할 수 있다는 문제점을 가지고 있다. 이 문제점을 해결하기 위해 나온것이 바로 HTTPS.  HTTPS 프로토콜은 TCP전송 계층 위에 SSL 보안 소켓 계층이 올라가서 서버와 브라우저간의 암호화된 연결을 만들게해주고, 이는 제 3자로부터의 데이터 탈취를 방지해준다. 따라서 HTTPS는 서버에서 전송할 내용을 공개키 또는 개인키로 암호화하여 SSL 인증서를 클라이언트에게 보낸다. 이렇게 되면 중간에 탈취가 되어도 암호화가 되어있어 개인정보가 침해되지않는다. 클라이언트는 이 SSL 인증서를 받게되면 공개키로 암호화되었다면 개인키로, 개인키로 암호화되었다면 공개키로 복호화하여 데이터를 전달 받게된다.
</details>

<details>
 <summary> 컨텍스트 스위칭에대해 설명해보시오. </summary>
</br>
- 여러 실행되고 있는 프로그램, 즉 프로세스들이 동시에 실행되고있는거 같지만 사실 운영체제는 시분할을 이용해서 굉장히 빠른속도로 여러 프로세스들을 번갈아가며 처리해서 마치 동시에 처리되는것처럼 보이는 것이다. 이때 인터럽트가 발생하면 CPU가 다음에 실행될 프로세스를 가져오고 레지스터에 해당 프로세스 정보를 저장한다. 그리고 기존에 실행중이던 프로세스는 PCB에 프로세스 정보를 저장하고 실행이 종료되는 것이다. 이 과정을 컨텍스트 스위칭이라고 한다. 첨언하자면, 이 컨텍스트 스위칭 과정에서는 CPU가 아무런 일을 하지 않으므로 잦은 프로세스 변경은 성능 저하로 이어질 수 있다.
</details>

<details>
 <summary> 강한결합과 느슨한결합에 대해 설명해보시오.</summary>
</br>
- 객체의 의존 관계에서 강한 결합이란, 어떠한 객체가 다른 객체에 강한 의존성을 가지고 있음을 뜻한다. 쉽게 말하면 한 객체 클래스내에서 다른 객체를 직접 생성한다면 객체간의 강한 결합이라고 할 수 있다. 이렇게되면 클래스안에서 생성했었던 객체 정보가 바뀌게 된다면, 해당 클래스에서도 그 객체와 관련한 코드들을 수정해주고 이는 유지보수에 어려움을 일으킵니다. 이에 반해 느슨한 결합은 interface를 통해 구현이 가능한데, 객체 클래스에서는 다른 객체를 직접 생성하지않고, 생성자나 setter, 일반 메서드를 통해 해당 객체를 외부에서 매개변수로 받는다. 이때 받는 인자를 interface로 선언하여 외부에서 객체 정보가 바뀌어도 interface에 대한 또 다른 구현체일테니, 자바의 다형성의 특징때문에 주입받는 객체와 연결되어있는 인자정보를 바꿀 필요가 없고 이는 유지보수성이 용이하다고 할 수 있다.
</details>


## 2023-07-15

정규성
<details>
 <summary> 동기와 비동기의 차이(블로킹, 넌블로킹) / 장단점에 대해 설명해보세요. </summary>
</br>
 프로그래밍에서 여러개의 프로세스가 동시에 진행되다 보면 어떤 방식으로 프로세스를 처리할 지 결정해야 합니다. 이를 위해 크게 4가지 경우를 나눕니다.

동기, 비동기, 블로킹, 논블로킹

동기, 비동기는 작업의 순서를 나타냅니다.

- 동기(synchronous) : 작업 시간을 맞춰 진행합니다. 하나의 작업이 완료되면 다음 작업을 수행합니다.
- 비동기(asynchronous) : 동기와 반대로 요청 작업의 완료 여부를 따지지 않고 진행합니다.

블로킹, 논블로킹은 작업의 흐름을 막느냐를 나타냅니다. 제어권을 넘긴다고도 표현합니다.

- 블로킹 : A함수에서 B함수를 호출했다면 B함수에 제어권을 넘기고 A함수는 동작을 멈춥니다. B함수가 끝나면 A함수에게 제어권을 돌려줍니다.
- 논 블로킹 : A함수에서 B함수를 호출하더라도 제어권을 넘기지 않고 A함수는 그대로 실행하고 B함수도 실행합니다.

얼핏보면 동기와 블로킹, 비동기와 논블로킹을 같은 개념으로 볼 수 있지만 그렇지않습니다.

4가지 경우의 수가 나올 수 있습니다.

1. 동기 블로킹 : A함수는 B함수에게 제어권을 넘기고 함수가 끝나기까지 기다립니다. 이동안 A함수는 아무런 동작을 하지않습니다. 
2. 동기 논블로킹 : A함수는 B함수에게 요청하고 바로 다른 일을 수행하되, 주기적으로 작업이 완료됐는지 요청합니다. 완료를 기다리고 있기 때문에 동기, 제어권을 넘기지 않았기 때문에 논블로킹입니다.
3. 비동기 블로킹 : A함수는 B함수에게 요청하고 제어권을 넘긴다. 제어권이 없기 때문에 동작을 수행할 수는 없다. B함수는 제어권을 받고 동작을 수행하고 끝나면 값을 전달한다. 구현된 예시가 매우 적을 만큼 사용될 일이 없다.
4. 비동기 논블로킹 : A함수는 B함수에게 요청하고 동작을 계속한다. B함수는 요청에 따른 동작을 수행한 후 동작이 끝나면 값을 반환한다.
</details>

<details>
 <summary> JVM 에 대해 설명해주세요. </summary>
</br>
 JVM 은 자바 프로그램 실행환경을 만들어 주는 SW 입니다. java 파일을 컴파일한  class 파일을 실행할 수 있습니다. JRE 를 설치하면 포함되어 있습니다.

이렇게 어느 플랫폼이던 JRE 만 설치하면 class 파일을 실행할 수 있기 때문에 플랫폼에 독립적입니다. 다만 이 JVM 자체는 플랫폼에 맞게 제공해야 합니다.

컴파일 된 class 파일을 플랫폼에 맞는 JVM 에 맞는 파일로 변환합니다.

이제 이 파일을 읽고 해석하는 방식으로 interpreter 방식과 JIT 방식을 혼합하여 사용합니다. interpreter 방식은 한 줄씩 해석해서 실행합니다. 속도가 느립니다. 이를 보완하기 위해 JIT 컴파일 방식을 사용합니다. 모든 줄을 한 줄씩 해석하는 것이 아니라 컴파일러로미리 native code 로 변환하고 속도를 개선합니다. 하만 항상 사용하지는 않고 둘을 적절히 섞어서 사용합니다. 캐싱을 사용하여 바뀐부분에 대해서만 다시 해석하기 때문에 굉장히 빨라집니다.
 </details>

<details>
 <summary> JVM 의 내부 구조에 대해 설명해주세요 </summary>
</br>
 JVM의 동작방식

1. JAVA 프로그램을 실행하면 JVM 은 OS로 부터 메모리를 할당받습니다.
2. java 파일을 class 파일로 컴파일합니다.
3. class loader 를 총해 JVM Runtime Data Area 로 로딩합니다.
4. 올라온 class 를 Execution Engine 을 통해 해석합니다.
5. 해석한 코드를 Runtime Data Area의 각 영역에 배치합니다.

내부 구조

1. 클래스 로더 : class 를 로드하고 Runtime Data Area로 적재합니다.
2. 실행 엔진 : Runtime Data Area에 적재된 코드를 실행합니다. 바이트 코드를 명령어 단위로 읽어서 해성합니다.
3. 가비지 컬랙터 : 더는 사용하지 않는 메모리를 자동으로 회수합니다. Heap 영역에 적재된 객체들 중 참조되지 않는 객체를 제거합니다. 이때 GC를 제외한 다른 스레드는 일시정지 됩니다.

Runtime Data Area

Heap 과 Method 영역은 모든 스레드가 공유하고, 나머지는 스레드 별로 따로 가집니다.

1. Heap Area : new 키워드로 생성된 객체와 배열이 생성됩니다. GC가 동작합니다.
2. Method Area : 클래스 멤버 변수 이름, 데이터 타입, 접근 제어자, method 정보, 데이터 type 정보, const, static, final 값이 저장됩니다.
3. stack Area : 지역변수, 파라미터, 리턴 값, 임시값 등이 생성됩니다.
4. PC 레지스터 : Thread 가 생성될 때마다 생성되며, 현재 스레드가 실행되는 부분의 주소와 명령을 저장합니다.
5. Native Method Stack : 자바 이외의 언어로 작성된 native code 로 작성된 코드를 실행할 때 사용되는 영역입니다.
</details>

조준희
<details>
 <summary> JVM의 구조에 대해 설명해보시오. </summary>
</br>
JVM의 구조는 Class Loader, Execution engine, Runtime Data Area, Garbage Collector 로 이루어져 있다.

1. Class Lodaer : JVM 내의 클래스파일(.class)을 로드를 통해 Runtime Data Area 에 저장하고, 링크(검증, 준비, 분석), 초기화 하는 작업을 거친다.
   
3. Execution engine : Runtime Data Area에 저장된 바이트 코드들을 실행하는 역할을 한다.(인터프리터,JIT 컴파일러에 의해 실행)
   
5. Runtime Data Area : 프로그램이 실행되는 영역
   
7. Garbage Collector : 자바의 메모리 관리 방법 중의 하나로 JVM(자바 가상 머신)의 Heap 영역에서 동적으로 할당했던 메모리 중 필요 없게 된 메모리 객체(garbage)를 모아 주기적으로 제거하는 영역이다.
 
</details>

<details>
 <summary> 자바의 메모리구조에 대해 자세하게 설명해보시오.  </summary>
</br>
 
 자바의 메모리구조(Runtime Data Area)는 5가지로 구성되어있다.
 
 1) PC Register : Thread가 시작될 때 생성되며 현재 수행 중인 JVM의 명령어 주소를 가지고 있다.
    
 3) Stack Area : 지역 변수, 파라미터 등이 생성되는 영역이며 실제 객체는 Heap에 할당되고 해당 레퍼런스만 Stack에 저장된다. 스레드마다 한 개씩 가지고 있다.
    
 5) Heap Area : 동적으로 생성된 객체와 배열이 저장되는 곳으로 GC의 대상 영역이다. 한 프로세스내의 스레드들은 이 영역을 같이 공유할 수 있다.
    
 7) Method Area : 클래스 멤버 변수, 메소드 정보, Type 정보, Constant Pool, static, final 변수 등이 생성된다.
    
 9) Native Method Stack : Java 가 아닌 다른 언어 (C, C++) 로 구성된 메소드를 실행이 필요할 때 사용되는 공간
     
</details>

 <details>
 <summary> GC가 무엇인지, 필요한 이유는 무엇인지, 동작방식에 대해 설명해주세요. </summary>
 <br>
 GC는 자바의 메모리 관리 방법 중의 하나로 JVM(자바 가상 머신)의 Heap 영역에서 동적으로 할당했던 메모리 중 필요 없게 된 메모리 객체(garbage)를 모아 주기적으로 제거하는 영역이다. <br>
  
 다음 두가지 과정을 거치면서 GC가 이루어진다. <br>
 
 1. Stop The World
    - JVM이 애플리케이션의 실행을 멈추는 작업이다. GC가 실행될 때는 GC를 실행하는 쓰레드를 제외한 모든 쓰레드들의 작업이 중단되고, GC가 완료되면 작업이 재개된다.
      
 2. Mark and Sweep
    1) Mark: 사용되는 메모리와 사용되지 않는 메모리를 식별하는 작업
       - 힙 영역에 할당된 객체들이 Unreachable, reachable 인지 체크하는 과정이다.
    3) Sweep: Mark 단계에서 사용되지 않음(Unreachable)으로 식별된 메모리를 해제하는 작업
       - Unreachable 객체에 대해 가비지컬렉터가 수거해간다.(메모리에서 할당 되어있었던 해당 객체를 해제한다.)
    
</details>

## 2023-07-16

정규성
<details>
 <summary> 객체지향의 4가지 특징에 대해 설명해주세요 </summary>
</br>
 객체지향은 여러 독립적인 객체들의 유기적인 연결을 통해 프로그램을 만드는 패러다임입니다. 독립적 객체들의 연결으로 인해 보다 유연하고 변경이 용이해며, 코드의 변경이 최소화되며 유지보수에 용이합니다. 또, 이렇게 나눠진 객체들을 재활용하여 반복되는 코드를 줄있 수 있습니다. 객체는 실제 세계에 있는 것을 나타내기 때문에 직관적인 코드를 작성할 수 있습니다.

- 추상화 : 객체의 공통적인 속성과 기능을 추출하여 정리하는 것
- 상속 : 기존의 클래스를 재활용하여 새로운 클래스를 작성하는 문법
- 다형성 : 객체의 속성이나 기능이 상황에 따라 여러가지 형태를 가질 수 있는 성질
- 캡슐화 : 서로 연관있는 속성과 기능들을 하나의 캡슐로 만들어 데이터를 외부로부터 보호하는 것

</details>

<details>
 <summary> SOLID(객체지향 5대원칙)에 대해서 설명해주세요. </summary>
</br>
 좋은 설계를 통해서 추후에 새로운 요구사항이나 변경사항이 생겼을 때 영향을 받는 범위가 적게 만들기 위해 적용하는 원칙입니다.

- SRP(단일책임원칙) : 객체는 하나의 기능을 담당하여 하나의 책임을 수행해야합니다. 한 책임의 변경으로부터 다른 책임의 변경으로 연쇄작용을 극복할 수 있습니다.
- OCP(개방 폐쇄 원칙) : 확장에 열려있어야 하며, 수정에는 닫혀있어야 한다.
- LSP(리스코프 치환 원칙) : 서브 타입은 언제나 기반 타입으로 교체할 수 있어야 한다.
- ISP(인터페이스 분리 원칙) : 인터페이스를 각각 사용에 맞게 끔 잘게 분리해야한다.
- DIP(의존 역전 원칙) : 어떤 class 를 참조해야 하는 상황이 생기면, 그 상위 요소로 참조해야한다.
 </details>

<details>
 <summary> WebSocket 에 대해 설명해주세요. </summary>
</br>
 http와 비교할 수 있습니다. http는 request 와 response 를 주고받아야 합니다. 이는 http가 stateless 하기 때문입니다. 

websocket은 연결이 되어 있다면 서로 자유롭게 메시지를 보낼 수 있습니다. 처음 연결을 위해 http 와 동일하게 handshake 과정을 거칩니다. 이후에는 서버에 누가 접속했는지 확인할 수 있으며 서로 순서없이 메시지를 보낼 수 있습니다.

웹 브라우저는 기본적으로 websocket이 내장되어 있으며, server에는 별도의 패키지 혹은 라이브러리가 필요합니다.
</details>

조준희
<details>
 <summary> 웹소켓통신과 HTTP 통신의 차이점을 설명해봐라. </summary>
</br>
웹소켓과 HTTP 통신의 차이점은 상태를 유지하는(Stateful) 여부와 양방향, 단방향 통신의 차이라고 생각한다. 
 
 웹소켓 통신은 클라이언트와 서버간의 실시간 양방향 통신이 가능하도록 만들어진 통신 프로토콜이다. Stateful한 프로토콜이므로 
 한번 TCP로 연결되면 같은 연결로 통신을 계속해서 진행할 수 있어서 TCP 커넥션 비용을 아낄 수 있다. 또한 양방향(양방향,duplex) 통신이기때문에, 
 클라이언트가 따로 새로고침이나, 특정 액션으로 request 요청하지않아도 서버로부터 데이터를 받을 수 있다. 
 그렇기때문에 실시간 채팅, 구글 Docs, 멀티플레이 게임, 화상 회의등에서 웹소켓 통신을 사용한다.

 HTTP 통신은 무상태(Stateless)한 특징을 가지는 프로토콜로, 매 요청때마다 TCP를 연결하고 해제하는 과정을 거친다. 
 그렇기 때문에 그만큼 네트워크 리소스를 차지하게 된다. 그리고 Stateless 서비스는 가용성을 제공하기 위해서 여분의 인스턴스를 추가하고 로드 벨런스를 사용한다. 
 또한 HTTP 프로토콜은 단방향 통신이기 때문에, 클라이언트의 특정 요청 없이는 서버로부터 데이터를 받을 수 없다. 
 
</details>

<details>
 <summary> 소켓? 도대체 소켓이 뭐냐? </summary>
</br>
 소켓은 컴퓨터 네트워크에서 프로세스 간 통신을 가능하게 하는 연결부라고 볼 수 있다. 소켓은 전송 계층과 응용프로그램 사이의 인터페이스 역할을 하며 떨어져 있는 두 호스트를 연결해준다. 데이터를 통신할 수 있도록 연결해주기 때문에 통신할 클라이언트와 서버 모두에 소켓이 생성되어야 한다. 
흠.... 진짜 잘 모르겠따... 흠...........
</details>

 <details>
 <summary> OSI 7계층에 대해서 설명해봐라. </summary>
 <br> 

 1. 물리계층
    - 주로 전기적, 기계적, 기능적인 특성을 이용해 데이터를 전송한다.
    - 단지 데이터 전달의 역할을 할 뿐이라 알고리즘, 오류제어 기능이 없다.
    - 장비로는 케이블, 리피터, 허브가 있다.
 2. 데이터 링크 계층
    - 물리적인 연결을 통하여 인접합 두 장치 간의 신뢰성 있는 정보를 위해 오류에 대해 재전송하는 기능을 가진다.
    - 데이터 단위를 프레임으로 Mac 주소를 통해서 통신한다.
    - 장비로는 브리지, 스위치가 있다.
 3. 네트워크 계층
    - 각 호스트에 IP 주소를 부여하고, 해당 경로(목적지)로 패킷을 전달해주는 역할을 한다.
    - 데이터 단위는 패킷이다.
    - 장비로는 라우터, L3 스위치가 있다.
 4. 전송 계층
    - 포트를 열어서 응용 프로그램들이 통신할 수 있게 만든다.
    - 송신자와 수신자 간의 신뢰성있고 효율적인 데이터를 전송하기 위하여 오류검출 및 복구, 흐름제어와 중복검사를 수행한다.
    - 주로 TCP, UDP 프로토콜을 사용하며, TCP의 데이터 단위는 세그먼트, UDP의 데이터 단위는 데이터그램이다.
    - 네트워크 계층은 호스트 간의 논리적 통신을 돕지만, 전송 계층은 응용 프로세스 간의 논리적인 통신을 돕는다.
 6. 세션 계층
    - 네트워크상 연결을 관리하고 연결을 지속 시켜 주는 계층이다.
    - TCP/IP 세션을 만들고 유지한다.
    - 연결 세션에서 데이터 교환과 에러 발생 시의 복구를 관리
 7. 표현 계층
    - 코드 간의 번역을 담당하여 사용자 시스템에서 데이터의 형식 상 차이를 다루는 부담을 응용 계층으로부터 덜어 준다. 데이터 암호화, 복호화 등의 동작을 수행한다.
 8. 응용 계층
    - 사용자와 가장 밀접한 계층으로 인터페이스 역할, 사용자에게 보이는 유일한 계층이다.
    - 응용 프로세스 간의 정보 교환을 담당한다.
    - 메일 전송, 인터넷 접속 등의 작업을 수행할 수 있다.
</details>

