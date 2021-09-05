# Study_JavaBase-MSA
자바 기반의 마이크로서비스 이해와 아키텍처 구축하기(박성훈 지음)

## [Settings]

## [Origin Source]
* [출처](https://github.com/architectstory)

---

# 목차별 내용 정리

## Chapter01
마이크로서비스 아키텍처의 이해
* MSA(Micro Service Architecture)

소프트웨어 아키텍처의 정의
* 소프트웨어를 구성하는 요소와 요소 간의 관계를 정의한 청사진(도면)

아키텍처의 표현
* 사람마다 직군, 경험 등을 기준으로 하나의 시스템을 이해하는 수준이 다름
* 표준화된 모델링 언어를 통해 아키텍처를 표현하는 것이 효과적
  * UML(Unified Modeling Language) 등
* 관점 (아키텍처 뷰)
  * Logical View (논리적 뷰)
    * 소프트웨어를 구성하는 요소들의 관계 구조 표현
  * Process View (프로세스 뷰)
    * 소프트웨어 간 동적인 흐름, 스레드, 프로세스 등의 동시성 처리 표현
  * Implementation View (구현 뷰)
    * 논리적인 설계의 실제 구현 측면에서 소프트웨어의 구성, 구조 표현
  * Deployment View (배치 뷰)
    * 시스템에서의 소프트웨어 배치 표현
  * Usecase View (유스케이스 뷰)
    * 시스템의 사용 사례 표현
    * 이를 제외한 위 4개의 표현은 사용 사례를 충족, 표현하기 위한 관점

아키텍처의 역할
* 유연하면서 단단한, 명확한 설계는 오랜 풍파로부터 잘 견딜 수 있게 해줌
  * 개발자의 수고를 덜어주고, 시스템의 성능 등을 좌우
* 구성 요소 간 명확하고 효율적인 역할 관계를 기반으로 탄력적인 아키텍처 형성 가능

소프트웨어 아키텍처 스타일
* 특정 제약 조건에서 아키텍처의 방향, 접근 방법을 의미
  * 자신(요구 조건 등)을 잘 나타내면서 다양한 환경을 잘 수렴하도록 설계
* 시스템 요건을 충족시키기 위한 제약 조건을 가진 아키텍처 측면 접근 방법
* 스타일
  * 상황을 해결할 접근 방법을 제시
* 패턴
  * 시스템이 가지는 문제를 해결할 구체적인 해결 방안을 경험 사례를 기반으로 제시
* MSA도 기존 모놀리스(monolith) 앱 구조의 문제점을 해결하기 위한 접근 방법(스타일)

모놀리스에서 마이크로서비스로 변화
* 일반적으로 모놀리스는 앱에서 사용하는 데이터 또한 한 곳에 두고 참조하는 형태
* 하지만 현대 사회에서는 비즈니스가 빠르고 수시로 변화되며 시스템의 크기가 큼
  * 비즈니스 요구를 빠르게 반영하기가 쉽지 않음
  * 시스템 규모, 복잡도의 증가로 빌드, 배포의 너무 많은 시간과 노력을 할애하게 됨
* 모놀리스의 단점을 극복하고자 앱을 작은 앱으로 나누어 서비스하는 것이 마이크로 서비스

회색지대와 아키텍트
* 회색지대는 업무 영역(+기술적 측면)이 겹치는 애매한 영역
* 팀 간 경계의 틈을 메워주는 것이 아키텍트 집단

아키텍트 역할의 세분화와 변화
* 성공적인 프로젝트를 위해 아키텍트에게는 모든 기술 요소에 대해 높은 이해 수준이 요구됨
* 현대 사회에서 모든 분야에 정통하기는 불가능
  * 따라서 프로젝트가 어떤 아키텍처이건 아키텍트 역할에 대한 구분이 필요
* 아키텍트 역할
  * 소프트웨어
  * 프론트엔드
  * 프레임워크
  * 데이터
  * 인프라
  * 테크니컬
  * 기타

솔루션 아키텍트
* 과거 아키텍트들이 수행한 작업 대부분을 클라우드 플랫폼이 자동화된 기능으로 제공
  * 시스템 리소스 구성 및 할당과 관리, 모니터링, 빌드, 통합, 배포 등의 프로세스를 아래 기술을 기반으로 자동화, 시각화하여 제공
    * IaaS (Infrastructure as a Service)
      * 서버 리소스, 네트워크, 스토리지, 가상화 등을 제공
    * CaaS(Container as a Service)
      * 하이퍼 바이저의 대안인 컨테이너 계층까지 제공
    * PaaS(Platform as a Service)
      * 특정 언어나 프레임워크, 라이브러리 같은 플랫폼까지 제공
    * BaaS(Backend as a Service)
      * 앱 개발자를 위해 클라우드 서비스, 인증(회원 관리), 푸시 알림 등 서비스 제공
    * FaaS(Function as a Service)
      * 특정 이벤트에 반응하는 함수를 등록, 함수를 실행하는 서비스 제공
    * SaaS(Software as a Service)
      * 앱을 서비스 형태로 제공
    * XaaS(X as a Service)
      * 'as a Service'로 통칭되는 것들을 말한다
    * On-Premiss
      * 기존 운영 방식 (하드웨어부터 모든 설정 작업을 직접 수행)
    * 그 외 인증 권한, 모니터링, 로깅, AI 등 전문 기술이 필요한 영역까지 제공
* 따라서 아키텍트들은 새로운 솔루션들을 빠르게 습득, 조합하는 능력도 중요

마이크로서비스 아키텍처의 개념
* 아주 작은 단위로 동작하는 서비스가 구동되도록 시스템, 소프트웨어의 구성과 구성 요소 간 관계를 정의한 아키텍처
  * 서비스 중심 아키텍처
  * 하나의 스타일

모놀리스 아키텍처와의 차이점
* 기존 모놀리스는 앱의 크기, 규모가 클 경우 변경, 배포 등이 어려움
  * MSA는 결합도가 낮은 다수의 서비스로 이루어져 모놀리스에 비하여 쉬움
  * 앱의 기능뿐 아니라 데이터까지 분리하여 격리, 독립된 환경으로 구성되었다는 것이 차이점

서비스 지향 아키텍처 (Service Oriented Architecture)
* 전체 시스템을 데이터 중심이 아닌 서비스 중심으로 설계하는 아키텍처
* 5가지 특징
  * 서비스 계약(서비스 - 서비스 소비자)
    * 약속된 기능 수행, 여러 개의 서비스 버전
  * 서비스의 가용성
    * 타임아웃, 요청 경로 변경 기능
  * 보안
    * 서비스 간 호출 시 보안상 문제 주의
  * 트랜잭션
    * Read/Write DB 저장소 분리시 데이터의 일관성, 실시간 동기화 이슈 주의
    * SOA에서 DB는 BASE(Basically Available Soft State Eventual Consistency) 트랜잭션
      * BASE는 분산 데이터베이스의 특징을 나타내는 개념(기존 RDB의 ACID 개념과 대비)
      * Basically Available
        * Optimistic locking, Queue는 대표적인 기술 메커니즘 (가용성 중시)
        * 다수의 실패에도 가용성 보장, 다수의 스토리지에 저장
      * Soft State
        * 외부 전달 데이터로 상태가 도달된 시점에 갱신되는 것
      * Eventual Consistency
        * 일시적으로 비일관상태가 되어도 결국에는 두 노드의 데이터가 일관성 있는 상태가 되는 성질
  * 서비스 관리
    * 서비스가 많아지면 관계 정리가 필요
    * 과부하, 오류 상황에도 지속 가능한 서비스가 가능하도록 관리 (실시간, 시각화 - 모니터링)

SOA와 MSA간 차이
* 공통점 - 비즈니스 변화의 대응을 위한 서비스 중심의 아키텍처
* 차이점 - 서비스의 상대적 크기, 관심사, 오너십, 기술 구조
  * 서비스의 상대적 크기, 관심사
    * MSA에서 서비스는 작고 한가지의 일에 집중
    * SOA에서 서비스는 비즈니스에 집중
  * 오너십(OwnerShip)
    * MSA에서 서비스는 하나의 작은 팀에서 관리
    * SOA에서 서비스는 서로 다른 팀간의 상호 협업이 반드시 필요
      * 비즈니스 프로세스 흐름과 관련된 서비스를 공유, 연결 및 조합하여 새로운 서비스 구성
  * 서비스 공유의 정도 차이
    * MSA는 서비스 공유의 최소화를 지향
      * 서비스간 결합도를 낮춰 변화에 민첩하고 능동적으로 대응
    * SOA는 되도록 많은 서비스 공유를 지향
      * 서비스의 재사용을 높여 비용 절감, 품질을 높이는 것에 초점
  * 기술 방식의 차이
    * MSA는 서비스의 공유없이 독립적으로 실행되는 것을 지향
      * 필요하면 만들고 필요 없다면 폐기 > 탄력성
      * 독립된 서비스 간 REST API(Restful) 통신, 필요할 때마다 사용
      * REST API를 보고 호출, 결괏값만 활용하여 구현이 쉬움
    * SOA는 많은 서비스 공유를 위해 ESB를 이용하여 서비스 공유, 비즈니스 측면에서 재사용 강조
      * Enterprise Service Bus
      * 흩어져 있는 같은 역할의 서비스를 통합, ESB에 담아 필요할 때마다 사용
      * 통합된 서비스들을 UDDI 이라는 서비스 저장소에 등록  
        WSDL 이라는 서비스 명세서 공유  
        WSDL을 참고하여 stub 클래스를 생성 후 SOAP 통신  
        결합도가 높기 때문에 명세가 변경되는 경우 모든 클라이언트를 변경해야 함
        * UDDI (Universal Description Discovery and Integration)
        * WSDL (Web Service Description Language)
        * SOAP (Simple Object Access Protocol)

|       구분       |            MSA            |             SOA             |
|:----------------:|:-------------------------:|:---------------------------:|
| 사상             | 서비스지향                | 서비스지향                  |
| 서비스 오너십    | 조직(팀) 단위 자율성 부여 | 조직(팀) 간 협업            |
| 서비스 크기      | SOA 대비 작음             | MSA 대비 큼                 |
| 서비스 공유 정보 | 서비스 간 독립            | 서비스 공유                 |
| 서비스 공유 방식 | API                       | 서비스 공유를 위한 미들웨어 |
| 서비스 통신 방식 | RESTful API 등            | SOAP, WSDL, UDDI, ESB 등    |

왜 MSA인가?
* 민첩한 서비스
  * 빠르게 변화하는 현대 비즈니스 환경에 대처하기 위해서는 빠르게 구현, 배포 되어야 함
  * 세분화하여 각각의 조직이 자율적, 독립적으로 서비스를 생성, 배포하여 능동적으로 대처
* 유연한 인프라
  * MSA를 가능케 하는 기술 환경 등장 (클라우드, 컨테이너 등)
  * 서비스 비즈니스와 실현을 도와줄 기술과의 조화
* Happy Path
  * 빠르게 개발, 검증할 수 있는 특성으로 해피 패스를 구현하기에 적절
  * 최소 기능만을 도출하여 향후 방향성 설정, 사전에 결과 체험

정리
* 해당 챕터에서는 MSA에 대한 개념, 특징과 기존 아키텍처와의 차이 등을 정의
* MSA는 DDD, 도커-쿠버네티스 등과 밀접한 관계까 있음
* 마이크로 서비스 간 REST API 뿐 아니라 최근에 나온 gRPC 또한 적용 가능할 것으로 보임

---

## Chapter02
클라우드 네이티브의 이해
* 클라우드 네이티브(Cloud Native)는 클라우드 환경에 친화적인 앱, 아키텍처, 인프라 등의 환경을 의미
* 비즈니스를 위한 기술 > 기술에 의한 비즈니스로 패러다임 전환

클라우드 네이티브 앱
* 클라우드 네이티브 환경에서 SaaS, FaaS 등 형태로 서비스 되는 앱

마이크로 서비스
* 서비스가 작고 독립적일수록 더 민첩한 환경 구성 가능
* 기존 서비스를 결합하여 새로운 서비스 생성
* 일반적으로 2주 안에 독립적으로 개발, 배포 가능한 정도의 크기를 권고
* 도커 등의 기술로 쉽고 간편하게 서비스를 생성, 삭제 가능

SaaS
* 설치형이 아닌 특정 기간, 특정 기능을 필요한 만큼 구매하여 사용하는 주문형 소프트웨어 서비스
* 기존 모놀리스 환경의 앱과는 다른 사상으로 개발되어야 함
* 가용성, 소스 버전 관리 중요

12팩터(Factor)
* 12팩터는 SaaS가 가져야 할 특성과 패턴
  * 코드베이스
    * 하나의 코드 베이스 버전으로 추적 관리되어야 함
    * 여러 서버 환경에 배포될 수 있지만 원본 소스는 하나인 것을 의미
  * 종속성
    * 사용되는 라이브러리들은 암묵적인 종속성이 발생하지 않아야 함
    * 명시적 선언 그리고 이외에 종속성이 오류를 유발하지 않을 것
  * 환경설정
    * 코드와 환경설정 정보는 완전히 분리되어 관리되어야 함
    * DB 연결정보, 호스트명, 백엔드 서비스의 리소스 정보 등
  * 백엔드 서비스
    * DB, 메시지 큐가 대표적이며 연결, 분리할 때 앱 코드를 수정하지 않고도 연결 가능할 것
    * 리소스의 추가, 분리가 자유로울 것
    * 리소스 식별자는 URI(Uniform Resource Identifier)
  * 빌드, 릴리스 및 실행
    * 소스 코드는 빌드, 릴리스, 실행 단계로 분리되어 운영
      * 빌드
        * 코드 저장소에 저장된 코드를 실행 가능한 형태로 변환 시키는 과정
        * 빌드 파일에 선언된 라이브러리는 종속성 확인 후 결합, 컴파일 됨
      * 릴리스
        * 환경설정 정보를 포함하여 즉시 실행이 가능한 상태로 만드는 과정
      * 실행
        * 런타임 환경으로 전환하는 과정
  * 프로세스
    * 무상태로 실행되며, 상태 정보를 공유하지 않아야 함
      * 필요하다면 DB 등과 같은 저장소 사용
      * 예를 들어 `sticky session` 등과 같은 것은 피해야 함
  * 포트 바인딩
    * 포트를 이용해 다른 서비스들과 구분하여 실행 가능
    * 포트로 바인딩되는 독립된 서비스들은 다른 서비스의 백엔드 서비스로 활용 가능
  * 동시성
    * 시스템 부하 발생 시 스케일 업보다는 스케일 아웃으로 대응하는 모델 형태일 것
  * 폐기 가능
    * 그레이스 풀 셧다운(graceful shutdown)이 보장되어야 함
    * 예상치 못한 상황에도 대응할 수 있는 논리적 메커니즘 필요
    * 최대한 빠르게 시작되며, 종료시엔 안전하게 종료
  * 개발, 테스트, 운영 환경의 일관성
    * 개발 환경은 테스트, 운영 환경과 최대한 같아야 함
  * 로그
    * 로그는 스트림 이벤트로 취급, 앱에서 가공 및 관리 등 관여하지 말아야 함
    * 이를 수집 전달할 수 있는 오픈 소스 이용
  * 일회성 프로세스
    * 일회성 작업은 별도의 프로세스 구성
      * 관리자 관련 작업, 유지 보수 관련 작업 등

FaaS
* 서비스의 수준을 기능 단위까지 세분하여 제공하는 서비스
* 직접 개발하지 않을 수 있고 즉시 사용 가능
* 이미 검증된 서비스를 사용하면 어느 정도의 수준이 보장 됨

확장 가능한 아키텍처
* 기존 모놀리스 구조에서는 하나의 인스턴스에서 앱이 실행되기 때문에 확장이 쉬운 구조가 아님
* 클라우드 네이티브 아키텍처는 수평적 확장이 쉬움

탄력적 아키텍처
* 서비스 생성-통합-배포, 비즈니스 환경 변화에 대응 시간을 단축, 오류를 예측하고 적절히 대응할 수 있는 구조
* 모놀리스 환경
  * 스케일업에 중점을 둔 백업, 복구 메커니즘 고려
* 클라우드 네이티브 아키텍처 환경
  * 수평적 확장에 초점
* 수평적 확장이 쉽고 복원력이 좋은 아키텍처의 특징
  * 분할된 서비스 구조
    * 장애 발생 시에도 서로 다른 서비스간에 영향 최소화
  * 무상태 통신 프로토콜 구성
    * 상태를 갖고 있다면 특정 서버의 문제가 클라이언트 측면에서 장애와 연결될 수 있음
  * 회로 차단
    * circuit breaker, 오류 발생 시 서비스 대신 처리 경로를 대체할 수 있는 응답을 보내 장애 회피

장애 격리
* 논리적인 격리는 서비스를 완전히 독립적으로 나누는 것으로 조치
* 물리적인 격리는 서비스를 단독으로 중지, 기동, 수정, 배포 가능한 인프라 환경 제공

컨테이너 기반 패키지
* 말 그대로 컨테이너 단위의 패키지
* 다만 패키지 단위가 시스템일 수 있고, 서비스 앱일 수 있음
* 컨테이너로 패키지된 단위가 실행 단위

동적 관리
* 컨테이너 단위로 패키지된 서비스가 추가, 삭제될 시 자동 감지, 요청을 처리할 수 있도록 관리 됨

CI
* 지속적인 통합
  * 개발 중인 코드를 통합하고, 테스트로 병행 수행하는 일련의 프로세스
* CI 서버
  * 젠킨스
* 소스 관리
  * Git, SVN
* 빌드 도구
* 테스트 도구

CD
* 지속적 배포
* Continuous Delivery
  * 빌드된 소스 코드의 실행 파일을 반영 전 단계까지 배포하는 방식
  * 허가 필요, 배포 수동
* Continuous Deployment
  * 빌드된 소스 코드의 실행 파일을 실행 환경까지 자동으로 배포하는 방식

파이프라인
* 통합 및 배포까지 일련의 프로세스를 하나로 연결하여 자동화, 시각화한 프로세스 구축

카나리 배포
* 요청 트래픽을 조절해 일부 사용자에게만 배포하여 정상 유무 확인

블루그린 배포
* 새로운 버전의 환경을 구성하여 요청 트래픽을 라우팅 처리 후 기존 환경 중지

데브옵스
* 데브옵스(DevOps)는 앱과 서비스 개발, 배포 운영까지 빠르게 제공하기 위한 조직의 협업 문화
* 이상적인 팀 구성 모델은 기획, 서계, 개발, 배포, 운영까지 서비스 생명주기가 한 팀에 의해서 결정되고 수행되는 형태
  * 팀 구성은 기획자, 아키텍트, 설계자, 개발자, 디자이너 등으로 구성
* 의사결정 권한, 자율적 조적, 업무별 담당자들이 한 팀을 구성하는 온전한 팀(Whole team) 지향

자동화와 시각화
* 프로세스 전체 과정이 자동화, 시각화되는 것이 이상적인 환경

컨테이너
* 리눅스의 격리 개념 존재
  * 독립된 공간 할당, 서로 격리되어 안전하게 실행

프로세스 격리
* 격리된 공간에서 수행되는 프로세스는 다른 공간에서 동작하는 프로세스에 영향을 받지 않음

가상화와 컨테이너
* 가상화는 하이퍼바이저(Hypervisor)라는 소프트웨어를 이용하여 하나의 물리 시스템에서 여러 운영체제를 사용할 수 있게 지원하는 기술
  * 하이퍼바이저는 하드웨어 시스템을 논리적인 단위로 나눠 별도의 공간을 할당하는 역할
  * 격리된 공간이 가상 머신(Virtual Machine), 여기에 설치된 OS가 Guest OS
* 컨테이너는 하이퍼바이저 없이 컨테이너 엔진을 통해 가상의 격리된 공간을 생성하는 기술
  * OS의 자원을 공유하지만 프로세스 간 격리를 통해 독립성을 부여
* Hypervisor + Guest OS > Docker Container

리눅스 컨테이너
* 컨테이너 기술을 적용하고 있고, 호스트 운영체제 위에 여러 컨테이너를 구성할 수 있는 운영체제 수준의 가상화 기술
* 네임스페이스(Namespace), 컨트롤그룹(CGroups), 커널(Kernel) 기능을 사용하여 격리된 공간을 관리

네임스페이스
* 컨테이너별로 격리된 공간을 가질 수 있도록 지원하는 기술

|               구분               |                              설명                              |
|:--------------------------------:|:---------------------------------------------------------------|
| PID(Process ID)                  | 각 프로세스에 할당된 고유한 ID                                 |
| NET(Network)                     | 네트워크 디바이스, IP, 포트, IP 테이블 등                      |
| MNT(Mount)                       | 컴퓨터 시스템에 접속되어 있는 디바이스 정보를 운영체제에 인식  |
| UID                              | 네임스페이스별로 user ID, group ID 할당                        | 
| UTS                              | 네임스페이스별로 호스트명, 도메인명을 독자적으로 가짐          |
| IPC(Inter Process Communication) | 프로세스 간 통신 객체를 네임스페이스별로 할당                  |

컨트롤그룹
* 물리적인 하드웨어 리소스를 프로세스 그룹 단위로 제어하는 커널 기능
  * 중앙처리장치, 메모리, 블록 입출력, 네트워크, 디바이스 노드 등과 같은 자원
  * 컨테이너의 재기동 없이 할당할 수 있게 해주는 기능

도커 이미지
* 도커 이미지는 하나 이상의 이미지 레이어로 구성, 도커 엔진에서 사용하는 기본 단위

도커 컨테이너
* 도커 이미지를 독립된 공간에 할당, 실행한 런타임 객체

도커 레지스트리
* 도커 이미지를 관리할 수 있게 제공된 저장 공간

도커 네트워크
* 도커 컨테이너 단위로 서비스할 수 있도록 네트워크 환경을 제공하는 가상의 네트워크 환경
  * 이를 가상의 브리지 `docker0`가 담당
  * 도커 데몬이 기동된 후, IP가 할당되고, 도커 컨테이너들도 컨테이너별 `eth0`에 IP가 자동으로 할당됨
  * 외부 퍼블릭 네트워크에서 들어오는 연결은 물리 `NIC(eth0)`와 연결
  * `NIC(eth0)`는 도커 내부 네트워크와 브리지 역할은 하는 `docker0`와 연결
  * `docker0`은 도커 내부 컨테이너들의 가상의 `NIC(veth)`와 연결되어 접속 가능
  * 도커 내부 컨테이너들은 각자 가상의 `eth0`에 IP가 자동으로 할당, `docker0`에서는 컨테이너의 IP를 확인하여 연결 가능
* 도커 네트워크는 NAPT(Network Address Port Translation) 사용
  * 하나의 IP를 가지고 가상의 여러 IP, 포트로 변환하는 기능
  * NAT(Network Address Translation)과 다름
    * NAT는 공용 IP와 사설 IP 관계가 1:1로 변환하는 방식
    * NAPT는 포트까지 변환하여 1:N으로 변환하는 방식
  * 도커는 리눅스의 IP 테이블을 NAPT로 사용

도커와 마이크로서비스
* 마이크로서비스는 독립된 서비스, 이를 실행하기 위한 환경이 도커 기술과 잘 어울림

정리
* 기술에 의한 비즈니스라는 패러다임 전환을 이야기 하며 이에 필요한 기술들의 대한 설명
* 클라우드 네이티브의 개념은 클라우드 컴퓨팅 모델을 사용하는 것을 전제로 설계된 시스템과 서비스
  * 클라우드 컴퓨팅 모델
* 클라우드 + 도커 + K8S 등의 기술 조합은 MSA 구성에 있어서 가히 필수적 요소라고 생각됨
  * 이와 동시에 Message Q나 RestAPI(또는 gRPC) 등도 함께 설명했다면 더 좋았을 듯
* MSA는 현대 사회의 비즈니스 환경이 변화 폭도 크게 영향이 있지만 기술 발달의 영향도 무시할 수 없다고 보임
  * 비즈니스가 복잡해지더라도 이를 받쳐줄 기술이 없었다면 구축, 구현하기 어려움
* K-Native, GitOps 등과 같은 관련 용어들도 확인 필요

---

## Chapter03
마이크로서비스 이해와 기획
* 마이크로서비스의 특성 중 하나는 소규모 조직이 독립적으로 개발, 배포할 수 있는 서비스라는 것
* 따라서 이 마이크로서비스를 나누는 관심사의 분리가 핵심 중 하나
  * 관심사를 나누는 기준, 크기 등 고려하여 형태와 크기를 결정

마이크로서비스와 MSA
* 서비스는 유연한 구조를 만들기 위한 분석 활동의 결과물
  * 기존 모놀리스 앱을 기준에 맞춰 서비스를 잘 나눈것이 마이크로서비스
* MSA는 이 결과물을 잘 설계하기 위한 아키텍처 중 하나
  * 마이크로서비스 형태 설계, 구현, 운영 등에 대해 적절한 방법을 찾는 것

마이크로서비스의 특징
* 작은 서비스
  * 서비스간 관계를 파악하여 경계와 크기를 잘 가늠하여 비즈니스를 작은 서비스로 나눔
    * 바운디드 컨텍스트(Bounded Context)
    * 유비쿼터스 언어(Ubiquitous Language)
* 독립된 서비스
  * 독립적으로 실행 가능하며, 다른 서비스와의 결합도가 낮은 서비스
    * 구현, 배포, 실행 같은 측면은 물론 장애 또한 영향을 받지 않아야 함
* 응집된 서비스
  * 하나의 서비스는 기능적으로 응집, 한 가지 일을 해결하기 위한 기능에 집중
    * 하나의 집중하면 단순, 명확해지고 장애 발생을 최소화 시킬 수 있음
* 자율적 서비스
  * 기획, 개발, 테스트, 배포, 운영까지 담당 조직이 소유권을 가지고 독립적으로 의사 결정, 관리

마이크로서비스 기획
* 기획을 위해서는 서비스 식별 전략이 필요
* 도메인, 비즈니스에 대한 이해

식별 전략
* 도메인 이해
  * 사용자 유형 분석
    * 사용자의 정의는 업과 관련된 모든 이해관계자
    * 사용자 분류 기준, 명칭, 역할, 권한과 조직 등을 분석하여 정의
  * 업무 흐름 분석
    * 데이터를 배제한 서비스 수준의 업무 흐름 분석
  * 핵심 업무, 우선순위
    * 핵심, 비핵심 업무로 분류
      * 비핵심 업무는 핵심 업무와 관련 정도를 파악
    * 업무 분류 후 우선순위 결정
  * 상관 분석
    * 참조 관계 또는 관계의 적절성을 파악하여 수평적 관계로 변경
      * 포함 관계 제거, 서비스의 역할과 기능 단순화
      * 데이터 상관관계 제거, 서비스 독립적으로 DB 구축
* 원칙 수립
  * 서비스 경계
    * 도메인, 기업 조직과 성격에 따라 다를 수 있어 어려움
    * 경계의 기준을 잘 판단(조직, 업무 중요도 등)
  * 서비스 분할
    * 하향식 접근
      * 업무의 흐름을 기준으로 나눔
      * 서비스에 사용하기 위한 데이터를 서비스별로 정의 하는 접근법
    * 상향식 접근
      * 데이터의 특성을 고려, 분할
      * 데이터를 기준으로 연관성이 없는 부분부터 분리
    * 점진적 접근
      * 비즈니스의 영향도가 덜한 서비스부터 하나씩 변경
* 상관관계 분석
  * 서비스와 데이터 간 종속성
    * 모놀리스에서는 하나의 저장소에 데이터를 통합하여 운영
    * MSA에서는 데이터의 경계를 넘어서까지 참조하는 관계를 지양
    * 서비스 관계에 따라 스키마 내부 또는 외부 관계 결정
  * 서비스 간 종속성
    * 서비스 기능 간 사용 관계를 분석하여 기능 간 결합도 파악
    * 업무 기능 단위 수준에서 분석 수준을 정할 것
    * 기능 내부 호출에서 REST URI 호출 형태로 변경
  * 데이터 간 종속성
    * 마이크로서비스 단위별로 DB 분리 권고
    * 분리 구성이 어려운 경우 스키마 분리를 통하여 서비스에 대응
    * 트랜잭션이 아닌 서비스 수준에서의 처리 또는 큐 메커니즘 활용하여 동기화
* 마이크로서비스 식별
  * 위 내용과 더불어 부서별 언어, 용어 등도 서비스의 영역을 구분하는데 참조

고려사항
* 조직의 구성
  * 소규모 팀 단위 (Whole team)
    * 규모가 클 경우 이해관계가 복잡하고 서비스 구축 시간이 큼
* 애자일과 데브옵스의 테일러링
  * 애자일 방법론, 데브옵스는 MSA와 궁합이 좋음
  * 점진적 개발 방식, 소통 문화 등 지향점 맥락이 같음
* 클라우드 네이티브 기술 환경
  * 과거 MSA 접근 방법이 어려웠던 이유 중 하나는 클라우드 네이티브 환경 미숙

정리
* DDD 또한 MSA와 뗄 수 없는 사이
* 커피 전문점은 굉장히 쉬운 도메인 사례이기 때문에 실제 업무 도메인으로 확인 필요

---
