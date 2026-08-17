# Week 06 - Cloud / DevOps Role-Based Interview 1

---

## 제출 기준

- 필수 답변: ROLE-001 ~ ROLE-020
- 선택 답변: ROLE-021 ~ ROLE-040

---

## 필수 질문

## [ROLE-001] 클라우드 컴퓨팅이 무엇이고, 온프레미스 환경과 어떤 차이가 있는지 설명해 주세요.

답변:

- 클라우드 컴퓨팅 (Cloud Computing)
  - 인터넷을 통해 컴퓨팅 자원(서버, 스토리지, 네트워크, DB 등)을 필요에 따라 사용하는 IT 서비스 모델
  - CSP(Cloud Service Provider)가 자원을 관리하고, 사용자는 사용량에 따라 비용을 지불 (Pay-as-you-go)
  - 자원을 빠르게 프로비저닝하고, 필요 시 확장·축소 가능
- 온프레미스 (On-Premise)
  - 기업이 자체 데이터센터에 서버·네트워크·스토리지를 직접 구매·설치·운영
  - 하드웨어 구매, 유지보수, 보안, 전력·냉각 등 인프라 전반을 자체 관리
- 차이
  - 비용: 클라우드는 사용량 기반 과금, 온프레미스는 초기 CAPEX(설비 투자) 비중 큼
  - 확장성: 클라우드는 즉시 스케일 업/다운, 온프레미스는 하드웨어 추가 구매·설치 필요
  - 관리 주체: 클라우드는 CSP가 인프라 관리, 온프레미스는 자체 IT 팀이 전담
  - 배포 속도: 클라우드는 분~시간 내 자원 생성, 온프레미스는 수주~수개월 소요 가능
  - 책임 범위: 클라우드는 Shared Responsibility Model, 온프레미스는 전체 책임

참고 자료:

---

## [ROLE-002] IaaS, PaaS, SaaS의 차이를 설명해 주세요.

답변:

- IaaS (Infrastructure as a Service)
  - 가상 서버, 스토리지, 네트워크 등 인프라를 제공
  - OS, 미들웨어, 애플리케이션은 사용자가 설치·관리
  - 예: AWS EC2, Google Compute Engine, Azure Virtual Machines
  - 관리 범위: 애플리케이션 ~ OS까지 사용자, 가상화 이하 CSP
- PaaS (Platform as a Service)
  - 애플리케이션 개발·실행을 위한 플랫폼(런타임, DB, 미들웨어) 제공
  - 인프라·OS·런타임은 CSP가 관리, 사용자는 코드·데이터만 관리
  - 예: AWS Elastic Beanstalk, Google App Engine, Heroku
  - 관리 범위: 애플리케이션·데이터만 사용자, 나머지 CSP
- SaaS (Software as a Service)
  - 완성된 소프트웨어를 웹/앱으로 제공
  - 설치·업데이트·인프라 관리 불필요, 즉시 사용
  - 예: Gmail, Slack, Salesforce, Microsoft 365
  - 관리 범위: 데이터·접근 권한만 사용자, 나머지 전부 CSP
- 차이
  - 사용자 관리 범위: IaaS(많음) → PaaS(중간) → SaaS(적음)
  - 유연성: IaaS(높음) → PaaS → SaaS(낮음)
  - 진입 장벽: SaaS(낮음) → PaaS → IaaS(높음)

참고 자료:

---

## [ROLE-003] Public Cloud, Private Cloud, Hybrid Cloud의 차이를 설명해 주세요.

답변:

- Public Cloud (퍼블릭 클라우드)
  - CSP가 소유·운영하는 클라우드, 다수 고객이 공유 (Multi-Tenant)
  - 인터넷을 통해 접근, 사용량 기반 과금
  - 예: AWS, GCP, Azure
  - 장점: 비용 효율, 즉시 확장, 관리 부담 적음
- Private Cloud (프라이빗 클라우드)
  - 단일 조직 전용 클라우드 환경
  - 온프레미스 데이터센터 또는 전용 호스팅에 구축
  - 장점: 보안·규제 준수, 커스터마이징, 데이터 주권
  - 단점: 구축·운영 비용 높음, 확장성 제한
- Hybrid Cloud (하이브리드 클라우드)
  - Public Cloud와 Private Cloud(또는 온프레미스)를 연결하여 함께 사용
  - 워크로드 특성에 따라 적절한 환경에 배치
  - 예: 핵심 DB는 Private, 웹 서버·배치는 Public
  - 장점: 유연성, 비용·보안 균형, 기존 인프라 활용
- 차이
  - 접근: Public은 공유, Private은 전용, Hybrid는 혼합
  - 보안·규제: Private > Hybrid > Public
  - 비용·확장성: Public > Hybrid > Private

참고 자료:

---

## [ROLE-004] 클라우드에서 Region과 Availability Zone이 무엇인지 설명해 주세요.

답변:

- Region (리전)
  - CSP가 클라우드 자원을 제공하는 지리적 영역 (국가·도시 단위)
  - 각 Region은 독립적인 데이터센터 클러스터로 구성
  - 예: AWS ap-northeast-2 (서울), us-east-1 (버지니아)
  - Region 간 데이터 전송은 네트워크 비용·지연 발생
  - 데이터 주권·규제 요구에 따라 Region 선택
- Availability Zone (AZ, 가용 영역)
  - 하나의 Region 내에 위치한 독립적인 데이터센터 (또는 데이터센터 그룹)
  - 각 AZ는 전력, 네트워크, 냉각이 분리되어 한 AZ 장애가 다른 AZ에 전파되지 않음
  - Region 내 AZ 간은 저지연 전용 네트워크로 연결
  - Multi-AZ 구성으로 High Availability 달성
- 관계
  - Region 1개 → AZ 여러 개 (예: 서울 리전에 4개 AZ)
  - 장애 격리: AZ 장애 → 같은 Region 내 다른 AZ로 전환
  - Region 장애 → Multi-Region 구성 필요

참고 자료:

---

## [ROLE-005] VPC가 무엇이고, 클라우드 네트워크에서 어떤 역할을 하는지 설명해 주세요.

답변:

- VPC (Virtual Private Cloud)
  - 클라우드 내에서 논리적으로 격리된 가상 네트워크
  - 온프레미스의 사설 네트워크를 클라우드에서 구현한 것
  - IP 주소 범위(CIDR), Subnet, Route Table, Gateway 등을 자유롭게 설계
- 주요 역할
  - 네트워크 격리: 다른 VPC·외부와 논리적으로 분리, 보안 강화
  - IP 주소 관리: Private IP 범위(예: 10.0.0.0/16)를 Subnet 단위로 분할
  - 접근 제어: Security Group, NACL로 인바운드·아웃바운드 트래픽 필터링
  - 연결성 제공: Internet Gateway, NAT Gateway, VPC Peering, VPN으로 외부·다른 VPC 연결
- 구성 요소
  - Subnet: VPC 내 IP 범위를 나눈 단위 (Public/Private)
  - Route Table: 트래픽 경로 정의
  - Internet Gateway: VPC와 인터넷 연결
  - Security Group / NACL: 트래픽 필터링

참고 자료:

---

## [ROLE-006] Public Subnet과 Private Subnet의 차이를 설명해 주세요.

답변:

- Public Subnet (퍼블릭 서브넷)
  - Internet Gateway(IGW)로 인터넷에 직접 접근 가능한 Subnet
  - Route Table에 0.0.0.0/0 → IGW 경로가 설정됨
  - Public IP 또는 Elastic IP가 할당된 리소스가 위치
  - 용도: Load Balancer, Bastion Host, NAT Gateway, 웹 서버(직접 노출 시)
- Private Subnet (프라이빗 서브넷)
  - 인터넷에서 직접 접근 불가, 외부로 나가는 트래픽은 NAT Gateway 등 경유
  - Route Table에 IGW 경로 없음, NAT Gateway 경로만 존재
  - 용도: 애플리케이션 서버, DB, 내부 API 서버
  - 보안: 외부에서 직접 접근 차단 → 공격 표면 축소
- 차이
  - 인터넷 접근: Public은 양방향 직접, Private은 아웃바운드만(NAT 경유)
  - 보안: Private이 더 안전, 핵심 자원은 Private에 배치
  - 일반적 구성: Public(LB, Bastion) + Private(App, DB) 2-Tier 또는 3-Tier

참고 자료:

---

## [ROLE-007] Security Group과 Network ACL의 차이를 설명해 주세요.

답변:

- Security Group (SG, 보안 그룹)
  - EC2, RDS 등 리소스 단위로 적용되는 가상 방화벽
  - Allow 규칙만 존재 (Deny 규칙 없음)
  - Stateful: 응답 트래픽은 자동 허용 (인바운드 허용 시 아웃바운드 응답 자동 통과)
  - 리소스에 1:N으로 연결 가능, 변경 즉시 적용
  - 예: EC2에 80, 443 포트 인바운드 허용
- Network ACL (NACL, 네트워크 ACL)
  - Subnet 단위로 적용되는 네트워크 레벨 필터
  - Allow와 Deny 규칙 모두 설정 가능
  - Stateless: 인바운드·아웃바운드 각각 명시적 규칙 필요
  - 규칙에 번호(Priority) 부여, 순서대로 평가
  - Subnet에 1:1 연결, 기본 NACL은 모든 트래픽 허용
- 차이
  - 적용 대상: SG는 리소스, NACL은 Subnet
  - 규칙: SG는 Allow만, NACL은 Allow + Deny
  - Stateful/Stateless: SG는 Stateful, NACL은 Stateless
  - 일반적 사용: SG로 주요 접근 제어, NACL로 Subnet 레벨 추가 차단

참고 자료:

---

## [ROLE-008] NAT Gateway가 무엇이고, 어떤 상황에서 사용하는지 설명해 주세요.

답변:

- NAT Gateway (Network Address Translation Gateway)
  - Private Subnet의 리소스가 인터넷으로 아웃바운드 통신할 때 Public IP로 변환하는 서비스
  - Private IP → NAT Gateway의 Public IP로 변환 후 인터넷 접근
  - 인바운드 연결은 허용하지 않음 (Private Subnet 보호)
- 사용 상황
  - Private Subnet의 EC2가 패키지 업데이트, 외부 API 호출, S3 접근 등이 필요할 때
  - DB 서버는 Private Subnet에 두되, 백업·패치를 위해 아웃바운드만 허용
  - 애플리케이션 서버가 외부 서비스(결제 API, 이메일 서비스) 호출 시
- NAT Instance vs NAT Gateway
  - NAT Instance: EC2로 NAT 구현, 관리 부담, 비용 저렴
  - NAT Gateway: AWS 관리형, 고가용성, 대역폭 보장, 권장 방식
- 배치
  - Public Subnet에 NAT Gateway 배치
  - Private Subnet Route Table: 0.0.0.0/0 → NAT Gateway

참고 자료:

---

## [ROLE-009] Load Balancer가 무엇이고, L4 Load Balancer와 L7 Load Balancer의 차이를 설명해 주세요.

답변:

- Load Balancer (로드 밸런서)
  - 들어오는 트래픽을 여러 서버(인스턴스)에 분산하는 서비스
  - 단일 장애점(SPOF) 제거, 가용성·확장성 향상
  - Health Check로 비정상 서버를 자동 제외
  - 예: AWS ALB, NLB, GCP Load Balancer
- L4 Load Balancer (Layer 4, Transport Layer)
  - IP 주소, 포트 번호 기준으로 트래픽 분산
  - TCP/UDP 레벨에서 동작, 패킷 내용을 해석하지 않음
  - 처리 속도 빠름, 낮은 지연
  - 예: AWS NLB (Network Load Balancer)
  - 용도: 고성능·저지연 필요, TCP/UDP 트래픽, WebSocket
- L7 Load Balancer (Layer 7, Application Layer)
  - HTTP/HTTPS 요청의 URL, Header, Cookie 등 내용 기준으로 분산
  - SSL/TLS 종료, 경로 기반·호스트 기반 라우팅 가능
  - 예: AWS ALB (Application Load Balancer)
  - 용도: REST API, 마이크로서비스, 경로별 다른 백엔드 연결
- 차이
  - 분산 기준: L4는 IP+Port, L7은 URL·Header·Cookie
  - 기능: L7은 라우팅·SSL 종료 등 애플리케이션 레벨 기능 제공
  - 성능: L4가 더 빠르고 가벼움

참고 자료:

---

## [ROLE-010] Auto Scaling이 무엇이고, 어떤 기준으로 확장 또는 축소할 수 있는지 설명해 주세요.

답변:

- Auto Scaling (오토 스케일링)
  - 트래픽·부하에 따라 인스턴스 수를 자동으로 늘리거나 줄이는 기능
  - 수요 변화에 대응하여 비용·성능을 최적화
  - AWS Auto Scaling Group(ASG)으로 구현
- 확장(Scale Out) 기준
  - CPU 사용률: 평균 CPU > 70% 등 임계값 초과 시 인스턴스 추가
  - 메모리 사용률: 메모리 부족 시 확장
  - 네트워크: 인바운드/아웃바운드 트래픽 임계값
  - 요청 수: ALB의 Request Count per Target
  - 커스텀 메트릭: CloudWatch 커스텀 지표 (큐 길이, 처리량 등)
- 축소(Scale In) 기준
  - CPU·메모리·트래픽이 임계값 이하로 하락 시 인스턴스 제거
  - Cooldown Period: 확장/축소 후 일정 시간 대기 → 급격한 변동 방지
- 설정 요소
  - Min / Desired / Max: 최소·희망·최대 인스턴스 수
  - Scaling Policy: Target Tracking, Step Scaling, Simple Scaling
  - Health Check: 비정상 인스턴스 자동 교체

참고 자료:

---

## [ROLE-011] IAM이 무엇이고, 최소 권한 원칙이 중요한 이유를 설명해 주세요.

답변:

- IAM (Identity and Access Management)
  - 클라우드 리소스에 대한 접근 권한을 관리하는 서비스
  - 사용자(User), 그룹(Group), 역할(Role), 정책(Policy)으로 권한 부여
  - 인증(Authentication): 누구인지 확인
  - 인가(Authorization): 어떤 리소스에 어떤 작업을 할 수 있는지 결정
- 주요 구성 요소
  - User: 개인 또는 서비스 계정
  - Group: User를 묶어 동일 권한 부여
  - Role: EC2, Lambda 등 서비스가 임시로 권한을 획득 (자격 증명 교환)
  - Policy: JSON 형식의 권한 문서 (Allow/Deny, Action, Resource)
- 최소 권한 원칙 (Principle of Least Privilege)
  - 업무 수행에 필요한 최소한의 권한만 부여
  - 과도한 권한(Administrator, *) 부여 금지
- 중요한 이유
  - 보안: 계정 탈취·내부자 위협 시 피해 범위 최소화
  - 규제 준수: 감사·컴플라이언스 요구 충족
  - 실수 방지: 의도치 않은 리소스 삭제·변경 방지
  - Blast Radius 축소: 한 계정·서비스의 장애가 전체에 전파되지 않음

참고 자료:

---

## [ROLE-012] Object Storage와 Block Storage의 차이를 설명해 주세요.

답변:

- Object Storage (객체 스토리지)
  - 데이터를 객체(파일 + 메타데이터) 단위로 저장
  - HTTP/REST API로 접근, 고유 Key(경로)로 식별
  - 무제한 확장, 높은 내구성(99.999999999%)
  - 예: AWS S3, GCP Cloud Storage, Azure Blob Storage
  - 용도: 이미지, 동영상, 백업, 정적 웹 호스팅, 데이터 레이크
  - 특성: 파일 단위 접근, 수정 시 전체 객체 교체
- Block Storage (블록 스토리지)
  - 데이터를 고정 크기 블록 단위로 저장
  - EC2 등에 마운트하여 OS·애플리케이션이 직접 읽기/쓰기
  - 낮은 지연, 높은 IOPS → DB, OS 디스크에 적합
  - 예: AWS EBS, GCP Persistent Disk
  - 용도: DB 데이터 파일, OS 루트 디스크, 애플리케이션 로컬 스토리지
  - 특성: 블록 단위 읽기/쓰기, 특정 EC2에 연결(일반적으로 1:1)
- 차이
  - 접근 방식: Object는 API, Block은 마운트 후 파일 시스템
  - 성능: Block은 저지연·고IOPS, Object는 대용량·고내구성
  - 용도: Object는 정적 파일·백업, Block은 DB·OS 디스크

참고 자료:

---

## [ROLE-013] 클라우드 환경에서 RDS와 같은 Managed Database를 사용하는 장단점을 설명해 주세요.

답변:

- Managed Database (관리형 DB)
  - CSP가 DB 설치, 패치, 백업, 복구, 모니터링을 관리
  - 예: AWS RDS, Aurora, GCP Cloud SQL, Azure SQL Database
- 장점
  - 운영 부담 감소: OS·DB 패치, 백업 자동화 → 개발에 집중
  - 고가용성: Multi-AZ, 자동 Failover, Read Replica 지원
  - 확장성: 스토리지 자동 확장, Read Replica로 읽기 부하 분산
  - 보안: 암호화(저장·전송), VPC 격리, IAM 연동
  - 백업·복구: 자동 백업, Point-in-Time Recovery
- 단점
  - 비용: 자체 구축 대비 사용량에 따라 비용 높을 수 있음
  - 커스터마이징 제한: DB 엔진 설정, 플러그인 등 제약
  - 벤더 종속: 특정 CSP·서비스에 의존
  - 성능 튜닝: 하드웨어·OS 레벨 최적화 불가
- 선택 시 고려
  - 운영 리소스가 부족하면 Managed DB 유리
  - 특수 DB 엔진·설정이 필요하면 Self-Managed 고려

참고 자료:

---

## [ROLE-014] CDN이 무엇이고, 정적 리소스 제공에 어떤 장점이 있는지 설명해 주세요.

답변:

- CDN (Content Delivery Network, 콘텐츠 전송 네트워크)
  - 전 세계 Edge Location에 콘텐츠를 캐시하여 사용자에게 가까운 위치에서 제공
  - Origin Server(S3 등)에서 콘텐츠를 가져와 Edge에 복제·캐싱
  - 예: AWS CloudFront, Cloudflare, Akamai
- 정적 리소스 제공 장점
  - 지연 시간 감소: 사용자와 가까운 Edge에서 응답 → Latency 단축
  - Origin 부하 감소: 캐시된 요청은 Origin에 가지 않음 → 서버 비용·부하 절감
  - 대역폭 비용 절감: Edge에서 제공 → Origin 전송 비용 감소
  - 가용성 향상: 분산된 Edge로 단일 장애점 제거
  - DDoS 방어: CDN이 대량 트래픽을 흡수·필터링
- 캐싱 대상
  - 이미지, CSS, JavaScript, 동영상, 폰트 등 정적 파일
  - Cache-Control, TTL 설정으로 캐시 유효 기간 관리
  - 동적 콘텐츠는 캐시하지 않거나 짧은 TTL 적용

참고 자료:

---

## [ROLE-015] Docker가 무엇이고, VM과 비교했을 때 어떤 차이가 있는지 설명해 주세요.

답변:

- Docker
  - 컨테이너 기반 애플리케이션 배포·실행 플랫폼
  - 애플리케이션과 의존성(라이브러리, 런타임)을 하나의 이미지로 패키징
  - 컨테이너: 호스트 OS 커널을 공유하는 격리된 실행 환경
  - 어디서든 동일하게 실행 (Build once, Run anywhere)
- VM (Virtual Machine)
  - 하이퍼바이저 위에 Guest OS를 포함한 완전한 가상화
  - 각 VM이 독립적인 OS, 커널, 하드웨어 에뮬레이션
- 차이
  - 격리 수준: VM은 OS 레벨 격리, Docker는 프로세스 레벨 격리
  - 리소스: VM은 Guest OS 포함 → 메모리·디스크 많이 사용, Docker는 가벼움
  - 시작 시간: VM은 수 분, Docker는 수 초
  - 이미지 크기: VM은 GB 단위, Docker는 MB 단위
  - 커널: VM은 각각 Guest OS, Docker는 호스트 커널 공유
  - 용도: VM은 완전 격리·다양한 OS 필요 시, Docker는 애플리케이션 배포·마이크로서비스

참고 자료:

---

## [ROLE-016] Container Image와 Container의 차이를 설명해 주세요.

답변:

- Container Image (컨테이너 이미지)
  - 컨테이너를 생성하기 위한 읽기 전용 템플릿
  - 애플리케이션 코드, 런타임, 라이브러리, 설정을 레이어(Layer)로 구성
  - Docker Hub, ECR 등 레지스트리에 저장·배포
  - 변경 불가(Immutable) → 수정 시 새 이미지 빌드
  - 예: `nginx:1.25`, `myapp:v1.0`
- Container (컨테이너)
  - 이미지를 기반으로 실행 중인 인스턴스
  - 이미지 위에 Writable Layer(컨테이너 레이어)가 추가됨
  - 실행·중지·삭제 가능, 고유 ID와 상태를 가짐
  - 컨테이너 삭제 시 Writable Layer도 삭제 (이미지는 유지)
- 관계
  - 이미지 1개 → 컨테이너 N개 실행 가능 (동일 이미지로 여러 인스턴스)
  - 클래스(이미지) vs 인스턴스(컨테이너) 관계
- Docker 명령어
  - `docker build`: 이미지 생성
  - `docker run`: 이미지로 컨테이너 실행
  - `docker pull/push`: 레지스트리에서 이미지 가져오기/올리기

참고 자료:

---

## [ROLE-017] Kubernetes가 무엇이고, 컨테이너 오케스트레이션이 필요한 이유를 설명해 주세요.

답변:

- Kubernetes (K8s)
  - 컨테이너화된 애플리케이션의 배포, 확장, 관리를 자동화하는 오픈소스 플랫폼
  - Google이 개발, CNCF에서 관리
  - Pod, Deployment, Service 등 리소스로 워크로드 정의
  - 예: EKS, GKE, AKS (클라우드 관리형 K8s)
- 컨테이너 오케스트레이션 (Container Orchestration)
  - 다수의 컨테이너를 클러스터에서 자동으로 배포·관리·확장하는 것
- 필요한 이유
  - 수동 관리 한계: 컨테이너 수가 늘면 배포·스케일링·장애 복구를 수동으로 불가능
  - 자동 스케일링: 부하에 따라 Pod 수 자동 조절 (HPA)
  - 자동 복구: Pod·노드 장애 시 자동 재생성·재배치
  - 서비스 디스커버리: 동적 IP·포트를 Service로 안정적 접근 제공
  - 로드 밸런싱: 트래픽을 여러 Pod에 자동 분산
  - 배포 자동화: Rolling Update, Rollback 등 배포 전략 지원
  - 멀티 노드: 여러 서버에 컨테이너를 분산 배치

참고 자료:

---

## [ROLE-018] Kubernetes의 Pod, Deployment, Service의 역할을 설명해 주세요.

답변:

- Pod
  - K8s에서 배포 가능한 최소 단위
  - 1개 이상의 컨테이너를 묶은 그룹, 동일 네트워크·스토리지 공유
  - Pod IP는 일시적 → Pod 재생성 시 IP 변경
  - 일반적으로 1 Pod = 1 컨테이너 (Sidecar 패턴 시 다수)
- Deployment
  - Pod의 desired state(원하는 상태)를 정의하고 관리
  - Replica 수, 이미지 버전, 업데이트 전략(Rolling, Recreate) 설정
  - Pod 장애 시 자동 재생성, Rolling Update로 무중단 배포
  - `kubectl apply`로 desired state 변경 → 실제 state를 맞춤
- Service
  - Pod 집합에 대한 안정적인 네트워크 엔드포인트 제공
  - Pod IP가 변해도 Service IP/도메인은 유지
  - 타입: ClusterIP(내부), NodePort, LoadBalancer(외부), ExternalName
  - Label Selector로 대상 Pod를 동적으로 선택
  - 로드 밸런싱: 요청을 Service에 연결된 Pod에 분산
- 관계
  - Deployment → Pod 생성·관리
  - Service → Pod에 안정적 접근 제공
  - 사용자/외부 → Service → Pod

참고 자료:

---

## [ROLE-019] CI/CD가 무엇이고, 빌드-테스트-배포 파이프라인의 흐름을 설명해 주세요.

답변:

- CI (Continuous Integration, 지속적 통합)
  - 코드 변경을 자주 통합하고, 자동 빌드·테스트로 품질 검증
  - 개발자가 Push/Merge 시 파이프라인 자동 실행
  - 조기 버그 발견, 통합 충돌 최소화
- CD (Continuous Delivery / Deployment)
  - Continuous Delivery: 빌드·테스트 통과 후 배포 준비 완료, 수동 승인 후 배포
  - Continuous Deployment: 테스트 통과 시 자동으로 프로덕션 배포
- 빌드-테스트-배포 파이프라인 흐름
  - 1. Trigger: Git Push, Pull Request, 스케줄 등으로 파이프라인 시작
  - 2. Source: 소스 코드 체크아웃 (Git clone)
  - 3. Build: 컴파일, Docker 이미지 빌드, 의존성 설치
  - 4. Test: 단위 테스트, 통합 테스트, 정적 분석, 보안 스캔
  - 5. Artifact: 빌드 결과물(이미지, 바이너리)을 레지스트리에 저장
  - 6. Deploy (Staging): 스테이징 환경에 배포, E2E 테스트
  - 7. Deploy (Production): 프로덕션 배포 (Rolling, Blue-Green 등)
  - 8. Monitor: 배포 후 헬스 체크, 알림, 롤백 준비
- 도구 예시
  - CI/CD: GitHub Actions, GitLab CI, Jenkins, ArgoCD
  - 빌드: Docker, Maven, Gradle
  - 배포: kubectl, Helm, Terraform

참고 자료:

---

## [ROLE-020] 무중단 배포가 무엇이고, Blue-Green 배포와 Rolling 배포의 차이를 설명해 주세요.

답변:

- 무중단 배포 (Zero-Downtime Deployment)
  - 서비스 중단 없이 새 버전을 배포하는 방식
  - 사용자는 배포 과정을 인지하지 못함
  - Health Check, 점진적 전환으로 안정성 확보
- Blue-Green 배포
  - Blue(현재 운영)와 Green(새 버전) 두 환경을 동시에 유지
  - Green에 새 버전 배포·테스트 완료 후, 트래픽을 Green으로 일괄 전환
  - 전환 실패 시 Blue로 즉시 롤백 (트래픽만 되돌리면 됨)
  - 장점: 롤백 빠름, 배포 중 두 환경 모두 검증 가능
  - 단점: 두 환경 동시 운영 → 리소스 2배 필요
- Rolling 배포
  - 기존 인스턴스를 점진적으로 새 버전으로 교체
  - 한 번에 일부만 업데이트, 나머지는 계속 서비스
  - K8s Deployment의 기본 전략 (maxSurge, maxUnavailable 설정)
  - 장점: 추가 리소스 최소, 점진적 전환
  - 단점: 롤백 시 역 Rolling 필요, 배포 중 Blue·Green 혼재 상태 존재
- 차이
  - 전환 방식: Blue-Green은 일괄 전환, Rolling은 점진적 교체
  - 리소스: Blue-Green은 2배, Rolling은 추가 최소
  - 롤백: Blue-Green은 즉시, Rolling은 시간 소요

참고 자료:

---

## 선택 질문

## [ROLE-021] 클라우드 비용 최적화를 위해 어떤 요소를 점검할 수 있는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-022] Infrastructure as Code가 무엇이고, Terraform 같은 도구를 사용하는 이유를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-023] Immutable Infrastructure가 무엇인지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-024] 클라우드 환경에서 Secret과 Credential을 안전하게 관리하는 방법을 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-025] CloudWatch, Prometheus, Grafana 같은 모니터링 도구가 각각 어떤 역할을 할 수 있는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-026] 로그, 메트릭, 트레이싱의 차이를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-027] 장애가 발생했을 때 클라우드 인프라 관점에서 어떤 순서로 원인을 분석할 수 있는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-028] Health Check가 무엇이고, Load Balancer나 Kubernetes에서 왜 중요한지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-029] Readiness Probe와 Liveness Probe의 차이를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-030] Horizontal Scaling과 Vertical Scaling의 차이를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-031] 클라우드 환경에서 High Availability를 설계할 때 고려해야 할 요소를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-032] Backup과 Disaster Recovery의 차이를 설명하고, RTO와 RPO에 대해 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-033] Multi-AZ 구성과 Multi-Region 구성의 차이를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-034] 클라우드 네트워크에서 DNS와 TLS 인증서가 어떤 역할을 하는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-035] API Gateway와 Load Balancer의 차이를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-036] Message Queue를 클라우드 아키텍처에서 사용하는 이유를 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-037] Kubernetes Ingress가 무엇이고, Service와 어떤 차이가 있는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-038] HPA가 무엇이고, 어떤 메트릭을 기준으로 동작할 수 있는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-039] 클라우드 보안에서 네트워크 보안, 접근 제어, 데이터 암호화를 각각 어떻게 고려해야 하는지 설명해 주세요.

답변:

참고 자료:

---

## [ROLE-040] 본인의 프로젝트에서 클라우드 인프라나 CI/CD를 구축했다면, 문제 상황, 선택 이유, 구성 방식, 결과를 어떻게 설명하면 좋을지 설명해 주세요.

답변:

참고 자료: