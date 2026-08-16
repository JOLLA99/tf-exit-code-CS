# Week 06 - Cloud / DevOps Role-Based Interview 1

---

## 제출 기준

- 필수 답변: ROLE-001 ~ ROLE-020
- 선택 답변: ROLE-021 ~ ROLE-040

---

## 필수 질문


아래와 같이 **각 답변은 1~2줄**, 참고자료는 가능한 한 **Velog/Tistory 1~2개**를 우선하여 정리했습니다.

---

## [ROLE-001] 클라우드 컴퓨팅이 무엇이고, 온프레미스 환경과 어떤 차이가 있는지 설명해 주세요.

답변:  
클라우드 컴퓨팅은 인터넷을 통해 서버·스토리지·네트워크 등의 컴퓨팅 자원을 필요한 만큼 사용하는 방식입니다. 온프레미스가 기업이 직접 장비를 구축·운영한다면, 클라우드는 공급자의 인프라를 필요에 따라 확장하며 사용합니다. 

참고 자료:  
- [Velog - 클라우드 컴퓨팅 개념 및 ASG](https://velog.io/@deok/%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%BB%B4%ED%93%A8%ED%8C%85-%EA%B0%9C%EB%85%90-%EB%B0%8F-ASG)
- [Velog - 클라우드 용어 정리](https://velog.io/@inop159/%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%9A%A9%EC%96%B4-%EC%A0%95%EB%A6%AC)

---

## [ROLE-002] IaaS, PaaS, SaaS의 차이를 설명해 주세요.

답변:  
IaaS는 서버·네트워크 등 인프라를, PaaS는 애플리케이션 실행 환경까지, SaaS는 완성된 소프트웨어 자체를 제공하는 형태입니다. 즉 IaaS → PaaS → SaaS로 갈수록 사용자가 직접 관리해야 하는 영역이 줄어듭니다. 

참고 자료:  
- [Velog - 클라우드 용어 정리](https://velog.io/@inop159/%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%9A%A9%EC%96%B4-%EC%A0%95%EB%A6%AC)
- [Velog - 일일 복습 4일차](https://velog.io/@9seob/%EC%9D%BC%EC%9D%BC-%EB%B3%B5%EC%8A%B5-4%EC%9D%BC%EC%B0%A8)

---

## [ROLE-003] Public Cloud, Private Cloud, Hybrid Cloud의 차이를 설명해 주세요.

답변:  
Public Cloud는 클라우드 사업자의 공유 인프라를 사용하는 방식이고, Private Cloud는 특정 조직만을 위한 독립적인 클라우드 환경입니다. Hybrid Cloud는 두 환경을 연동하여 워크로드나 데이터 특성에 따라 함께 사용하는 방식입니다.

참고 자료:  
- [Velog - Cloud Native의 이해](https://velog.io/@formin/Cloud-Native%EC%9D%98-%EC%9D%B4%ED%95%B4)
- [Velog - 클라우드 용어 정리](https://velog.io/@inop159/%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%9A%A9%EC%96%B4-%EC%A0%95%EB%A6%AC)

---

## [ROLE-004] 클라우드에서 Region과 Availability Zone이 무엇인지 설명해 주세요.

답변:  
Region은 클라우드 데이터센터가 위치한 독립적인 지리적 영역이며, Availability Zone(AZ)은 하나의 Region 안에서 물리적으로 분리된 데이터센터 그룹입니다. 여러 AZ에 서비스를 분산하면 장애에 대한 가용성을 높일 수 있습니다. 

참고 자료:  
- [Velog - Data Center와 클라우드](https://velog.io/@wearetheone/SK-shieldus-Rookies-19%EA%B8%B0-Data-Center%EC%99%80-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EB%8C%80%ED%95%B4-%EC%95%8C%EC%95%84%EB%B3%B4%EC%9E%90)
- [Velog - AZ 하나가 통째로 죽어도 살아남는 서비스 만들기](https://velog.io/@rocker_nun/AZ-%ED%95%98%EB%82%98%EA%B0%80-%ED%86%B5%EC%A7%B8%EB%A1%9C-%EC%A3%BD%EC%96%B4%EB%8F%84-%EC%82%B4%EC%95%84%EB%82%A8%EB%8A%94-%EC%84%9C%EB%B9%84%EC%8A%A4-%EB%A7%8C%EB%93%A4%EA%B8%B0)

---

## [ROLE-005] VPC가 무엇이고, 클라우드 네트워크에서 어떤 역할을 하는지 설명해 주세요.

답변:  
VPC(Virtual Private Cloud)는 클라우드에 논리적으로 격리된 가상 네트워크를 만드는 기능입니다. IP 대역, Subnet, Routing, 보안 정책 등을 정의하여 클라우드 리소스 간 네트워크 구조를 설계하는 기반이 됩니다. 

참고 자료:  
- [Tistory - AWS VPC 네트워킹 구성 실습](https://soy-ul.tistory.com/23)
- [Tistory - VPC : 서브넷과 구성 요소](https://sjh9708.tistory.com/253)

---

## [ROLE-006] Public Subnet과 Private Subnet의 차이를 설명해 주세요.

답변:  
Public Subnet은 Internet Gateway로 향하는 경로를 가져 외부 인터넷과 직접 통신할 수 있는 Subnet이고, Private Subnet은 인터넷에서 직접 접근할 수 없도록 구성한 Subnet입니다. 

참고 자료:  
- [Velog - 클라우드 용어 정리](https://velog.io/@inop159/%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%9A%A9%EC%96%B4-%EC%A0%95%EB%A6%AC)
- [Tistory - VPC : Public/Private Subnet, IGW, NAT Gateway](https://sjh9708.tistory.com/253)

---

## [ROLE-007] Security Group과 Network ACL의 차이를 설명해 주세요.

답변:  
Security Group은 인스턴스/네트워크 인터페이스 단위로 적용되는 Stateful 방화벽이고, Network ACL은 Subnet 단위로 적용되는 Stateless 접근 제어 기능입니다. NACL은 Allow와 Deny 규칙을 모두 지정할 수 있습니다. 

참고 자료:  
- [Tistory - AWS VPC 네트워킹 구성 실습](https://soy-ul.tistory.com/23)
- [Tistory - AWS 실습: NLB, ALB](https://miji-it.tistory.com/26)

---

## [ROLE-008] NAT Gateway가 무엇이고, 어떤 상황에서 사용하는지 설명해 주세요.

답변:  
NAT Gateway는 Private Subnet의 인스턴스가 Public IP 없이 외부 인터넷으로 통신할 수 있도록 주소를 변환해 주는 서비스입니다. 외부에서 직접 접근받을 필요는 없지만 패키지 다운로드나 외부 API 호출 등이 필요한 서버에 사용합니다. 

참고 자료:  
- [Tistory - VPC : 서브넷과 구성 요소](https://sjh9708.tistory.com/253)
- [Tistory - AWS VPC 네트워킹 구성 실습](https://soy-ul.tistory.com/23)

---

## [ROLE-009] Load Balancer가 무엇이고, L4 Load Balancer와 L7 Load Balancer의 차이를 설명해 주세요.

답변:  
Load Balancer는 들어오는 트래픽을 여러 서버에 분산하여 성능과 가용성을 높이는 장치입니다. L4는 IP·Port·TCP/UDP 정보를 기반으로, L7은 HTTP의 URL·Host·Header 등 애플리케이션 정보를 기반으로 분산합니다. 

참고 자료:  
- [Velog - 로드밸런서란?](https://velog.io/@alscjf6315/%EB%A1%9C%EB%93%9C%EB%B0%B8%EB%9F%B0%EC%84%9C%EB%9E%80)
- [Velog - AWS ALB, NLB 비교](https://velog.io/@yange/%EB%82%B4%EB%B6%80%EB%A7%9D%ED%8F%90%EC%87%84%EB%A7%9D%EC%97%90%EC%84%9C-repository-%EA%B5%AC%EC%84%B1)

---

## [ROLE-010] Auto Scaling이 무엇이고, 어떤 기준으로 확장 또는 축소할 수 있는지 설명해 주세요.

답변:  
Auto Scaling은 부하에 따라 서버 등의 리소스 수를 자동으로 늘리거나 줄이는 기능입니다. CPU 사용률, 네트워크 트래픽, 요청 수 등의 Metric이나 지정된 일정 등을 기준으로 Scale-out/Scale-in할 수 있습니다. 

참고 자료:  
- [Velog - 로드밸런서란? / Auto Scaling](https://velog.io/@alscjf6315/%EB%A1%9C%EB%93%9C%EB%B0%B8%EB%9F%B0%EC%84%9C%EB%9E%80)
- [Velog - 클라우드 컴퓨팅 개념 및 ASG](https://velog.io/@deok/%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%BB%B4%ED%93%A8%ED%8C%85-%EA%B0%9C%EB%85%90-%EB%B0%8F-ASG)

---

## [ROLE-011] IAM이 무엇이고, 최소 권한 원칙이 중요한 이유를 설명해 주세요.

답변:  
IAM(Identity and Access Management)은 사용자·서비스의 인증과 클라우드 리소스에 대한 접근 권한을 관리하는 기능입니다. 최소 권한 원칙은 업무 수행에 필요한 권한만 부여하여 계정 탈취나 실수 발생 시 피해 범위를 최소화하기 위해 중요합니다. 

참고 자료:  
- [Velog - 클라우드 용어 정리](https://velog.io/@inop159/%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%9A%A9%EC%96%B4-%EC%A0%95%EB%A6%AC)
- [Tistory - AWS 개념 정리](https://dbfl720.tistory.com/891)

---

## [ROLE-012] Object Storage와 Block Storage의 차이를 설명해 주세요.

답변:  
Object Storage는 데이터를 객체와 메타데이터 형태로 저장하여 이미지·백업 등 대용량 비정형 데이터 저장에 적합하고, Block Storage는 데이터를 고정 크기 블록으로 저장하여 VM 디스크나 DB처럼 빠른 I/O가 필요한 환경에 적합합니다.

참고 자료:  
- [Velog - 클라우드 용어 정리](https://velog.io/@inop159/%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%9A%A9%EC%96%B4-%EC%A0%95%EB%A6%AC)
- [Velog - Cloud 시리즈](https://prod.velog.io/@keithcha/series/Cloud)

---

## [ROLE-013] 클라우드 환경에서 RDS와 같은 Managed Database를 사용하는 장단점을 설명해 주세요.

답변:  
Managed Database는 DB 설치·백업·패치·장애 복구 등의 운영 부담을 클라우드 사업자가 대신한다는 장점이 있습니다. 반면 직접 구축하는 DB보다 비용이 높을 수 있고 세부 설정이나 특정 기능에 제약이 있어 공급자 종속성이 발생할 수 있습니다.

참고 자료:  
- [Velog - KT AIVLE Cloud Native 학습](https://velog.io/@mwkim-dev/KT-AIVLE-9%EA%B8%B0-Cloud-Native-%ED%95%99%EC%8A%B5%EA%B3%BC-6%EC%B0%A8-%EB%AF%B8%EB%8B%88%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EB%A7%8C%EB%93%A0-%EA%B2%83%EC%9D%84-%EC%84%B8%EC%83%81%EC%97%90-%EC%98%AC%EB%A6%AC%EA%B8%B0)
- [Velog - EC2·RDS·ECR 기반 백엔드 배포](https://velog.io/@gpekd5/%EC%B5%9C%EC%A2%85-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EB%B0%B0%ED%8F%AC-3-EC2RDSECR-%EA%B8%B0%EB%B0%98-%EB%B0%B1%EC%97%94%EB%93%9C-%EC%88%98%EB%8F%99-%EB%B0%B0%ED%8F%AC)

---

## [ROLE-014] CDN이 무엇이고, 정적 리소스 제공에 어떤 장점이 있는지 설명해 주세요.

답변:  
CDN(Content Delivery Network)은 여러 지역의 Edge 서버에 콘텐츠를 캐싱하여 사용자와 가까운 서버에서 전달하는 기술입니다. 이미지·CSS·JS 등의 정적 리소스 응답 시간을 줄이고 원본 서버의 트래픽 부담을 감소시킬 수 있습니다. 

참고 자료:  
- [Velog - 렌더링 전략과 CDN](https://velog.io/@kaeuhy/%EC%99%9C-CSR-SSR-SSG-ISR%EA%B0%80-%EC%A1%B4%EC%9E%AC%ED%95%A0%EA%B9%8C-HTML-%EC%83%9D%EC%84%B1-%EC%8B%9C%EC%A0%90%EC%9C%BC%EB%A1%9C-%EC%9D%B4%ED%95%B4%ED%95%98%EB%8A%94-%EB%A0%8C%EB%8D%94%EB%A7%81-%EC%A0%84%EB%9E%B5)
- [Velog - Fruit Box의 엣지 배포](https://velog.io/@scottdev/%EB%B0%B1%EC%97%94%EB%93%9C-%EC%97%86%EB%8A%94-%EC%82%AC%EA%B3%BC%EA%B2%8C%EC%9E%84%EC%97%90%EB%8F%84-%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98%EA%B0%80-%ED%95%84%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0-Fruit-Box%EC%9D%98-%ED%95%AD%EC%83%81-%ED%92%80-%EC%88%98-%EC%9E%88%EB%8A%94-%EB%B3%B4%EB%93%9C-i18n-%EC%97%A3%EC%A7%80-%EB%B0%B0%ED%8F%AC-i5ezzeco)

---

## [ROLE-015] Docker가 무엇이고, VM과 비교했을 때 어떤 차이가 있는지 설명해 주세요.

답변:  
Docker는 애플리케이션과 실행에 필요한 환경을 Container로 패키징하여 격리 실행하는 플랫폼입니다. VM이 각각 Guest OS를 포함하는 것과 달리 Container는 Host OS의 Kernel을 공유하므로 상대적으로 가볍고 빠르게 실행할 수 있습니다. 

참고 자료:  
- [Velog - Cloud Native의 이해](https://velog.io/@formin/Cloud-Native%EC%9D%98-%EC%9D%B4%ED%95%B4)
- [Velog - DevOps 엔지니어 Cloud Native 로드맵](https://velog.io/@nowd940/DevOps-%EC%97%94%EC%A7%80%EB%8B%88%EC%96%B4%EB%A5%BC-%EC%9C%84%ED%95%9C-Cloud-Native-%EC%8B%A4%EC%A0%84-%ED%95%99%EC%8A%B5-%EB%A1%9C%EB%93%9C%EB%A7%B5-1)

---

## [ROLE-016] Container Image와 Container의 차이를 설명해 주세요.

답변:  
Container Image는 애플리케이션 실행에 필요한 파일과 설정을 포함하는 변경되지 않는 실행 템플릿이며, Container는 해당 Image를 기반으로 실제 실행된 인스턴스입니다. 하나의 Image에서 여러 Container를 생성할 수 있습니다. 

참고 자료:  
- [Velog - 백엔드 CS 기초 한 번에 꿰기](https://velog.io/@hhho0coco1-star/backend-cs-basics)
- [Velog - MSA, Docker & CI/CD](https://velog.io/@jijiya/TIL-26-MSA-Docker-CICD-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EB%A6%AC%ED%8C%A9%ED%86%A0%EB%A7%81)

---

## [ROLE-017] Kubernetes가 무엇이고, 컨테이너 오케스트레이션이 필요한 이유를 설명해 주세요.

답변:  
Kubernetes는 여러 서버에서 동작하는 Container를 자동으로 배포·확장·복구·관리하는 Container Orchestration 플랫폼입니다. 컨테이너 수가 증가하면 사람이 일일이 배치하거나 장애를 복구하기 어려워지므로 이를 자동화하기 위해 필요합니다. 

참고 자료:  
- [Velog - Cloud Native의 이해](https://velog.io/@formin/Cloud-Native%EC%9D%98-%EC%9D%B4%ED%95%B4)
- [Velog - DevOps 엔지니어 Cloud Native 로드맵](https://velog.io/@nowd940/DevOps-%EC%97%94%EC%A7%80%EB%8B%88%EC%96%B4%EB%A5%BC-%EC%9C%84%ED%95%9C-Cloud-Native-%EC%8B%A4%EC%A0%84-%ED%95%99%EC%8A%B5-%EB%A1%9C%EB%93%9C%EB%A7%B5-1)

---

## [ROLE-018] Kubernetes의 Pod, Deployment, Service의 역할을 설명해 주세요.

답변:  
Pod는 하나 이상의 Container가 실행되는 Kubernetes의 최소 배포 단위이고, Deployment는 Pod의 복제본 수와 업데이트를 관리합니다. Service는 변할 수 있는 여러 Pod에 고정된 네트워크 접근점과 트래픽 분산 기능을 제공합니다. 

참고 자료:  
- [Velog - 백엔드 CS 기초 한 번에 꿰기](https://velog.io/@hhho0coco1-star/backend-cs-basics)
- [Velog - DevOps 엔지니어 Cloud Native 로드맵](https://velog.io/@nowd940/DevOps-%EC%97%94%EC%A7%80%EB%8B%88%EC%96%B4%EB%A5%BC-%EC%9C%84%ED%95%9C-Cloud-Native-%EC%8B%A4%EC%A0%84-%ED%95%99%EC%8A%B5-%EB%A1%9C%EB%93%9C%EB%A7%B5-1)

---

## [ROLE-019] CI/CD가 무엇이고, 빌드-테스트-배포 파이프라인의 흐름을 설명해 주세요.

답변:  
CI는 코드 변경 사항을 지속적으로 통합하여 자동 빌드·테스트하는 과정이고, CD는 검증된 결과물을 자동으로 배포하는 과정입니다. 일반적으로 코드 Push → Build → Test → Artifact/Image 생성 → 배포 순으로 Pipeline이 진행됩니다. 

참고 자료:  
- [Velog - KT AIVLE Cloud Native 학습](https://velog.io/@mwkim-dev/KT-AIVLE-9%EA%B8%B0-Cloud-Native-%ED%95%99%EC%8A%B5%EA%B3%BC-6%EC%B0%A8-%EB%AF%B8%EB%8B%88%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EB%A7%8C%EB%93%A0-%EA%B2%83%EC%9D%84-%EC%84%B8%EC%83%81%EC%97%90-%EC%98%AC%EB%A6%AC%EA%B8%B0)
- [Velog - MSA, Docker & CI/CD](https://velog.io/@jijiya/TIL-26-MSA-Docker-CICD-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EB%A6%AC%ED%8C%A9%ED%86%A0%EB%A7%81)

---

## [ROLE-020] 무중단 배포가 무엇이고, Blue-Green 배포와 Rolling 배포의 차이를 설명해 주세요.

답변:  
무중단 배포는 서비스 중단 없이 새로운 버전을 배포하는 방식입니다. Blue-Green은 기존·신규 환경을 동시에 구성한 뒤 트래픽을 전환하고, Rolling은 여러 인스턴스를 순차적으로 새 버전으로 교체합니다. 

참고 자료:  
- [Tistory - docker-compose Blue-Green 무중단 배포](https://jay-ji.tistory.com/99)
- [Tistory - Blue/Green 무중단 배포](https://jhzlo.tistory.com/82)

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