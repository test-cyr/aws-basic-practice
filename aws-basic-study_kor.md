# aws-basic-practice
AWS 기초개념과 실습정리

## 클라우드 컴퓨팅
* 클라우드 : 빌려쓰기
- IT 리소스를 인터넷을 통해 온디맨드로 제공하고 사용한 만큼 비용 지불
* 온디맨드 : 수요에 반응함
- 투자비용 적음
- 바로 사용 가능
- 유지보수 필요 X
- 유연한 사용 가능
- 사용한 만큼만 비용 지불 : OnDemand
* 장점 : 자본(초기)비용을 가변비용으로 대체 (막대한 초기비용 대신  사용한 만큼만)

## 클라우드 컴퓨팅 모델
- Software as a Service (공개형(클라우드) )
- Infrastructure as Service (혼합형(클라우드) )
- Platform as a Service (온-프레미스(폐쇄형) )

## 어플리케이션 구성
- OS : Window / Linux
- Computing : CPU + RAM
- Storage : HDD / SDD

* laaS : Infrastructure as a Service
  - 인프라만 제공
  - OS를 직접 설치하고 필요한 S/W 개발해서 사용
  - 가상의 컴퓨터를 하나 임대하는 것과 비슷
ex) AWS EC2
    레시피, 요리재료, 주방기기, 주방 (레시피, 요리재료 등은 user가 준비)
    * laaS 는 주방만 빌리는 것

* PaaS : Platform as a Service
  - 인프라 + OS + 기타 프로그램 실행에 필요한 부분 (런타임)
  - 바로 코드만 올려서 돌릴 수 있도록 구성
  ex) Firebase, Google App Engine 등
      * 주방기기, 요리재료 제공
       user는 레시피만 준비 (즉, 코드)

 * SaaS : Software as a Service : 인프라 + OS + 필요한 소프트웨어 제공
   - APP : 서비스 제공
   - OS : 다른 셋팅 없이 서비스만 이용
   - computing
   - storage
   - network
- 별도 설치없이 이용 가능

## 클라우딩 컴퓨팅 배포 모델
- 공개형 (클라우드)
  - 모든 부분이 클라우드에서 실행
  - 낮은 비용
  - 높은 확장성

- 혼합형 (클라우드)
  - 폐쇄형과 공개형의 혼합
  - 폐쇄형에서 공개형으로 전환하는 과도기에서 사용
  - 혹은 폐쇄형의 백업으로 사용
 
- 폐쇄형 (직접 클라우드 운영)
  - 높은 수준의 커스터마이징 가능
  - 초기비용 비쌈
  - 유지보수 비용 비쌈
  - 높은 보안
 
## AWS의 구조
- 리전 : AWS의 서비스가 제공되는 서버의 물리적 위치
         각 리전에는 고유의 코드가 부여됨
         리전별로 가능한 서비스가 다름
- ARN : AWS 리소스의 고유 아이디
- 가용영역 : 리전의 하부단위
             하나의 리전은 반드시 2개 이상의 가용영역으로 구성
             하나 이상의 데이터센터로 구성
             리전간 연결은 빠른 전용 network로 연결
             반드시 물리적 일정거리 떨어져 있음
 * 데이터 자체는 리전에 종속 : 리전 서비스
- 엣지 로케이션(Edge Location) : 임시 데이터 저장소 (즉, 거점)
                  AWS의 CloudFront (CDN) 등의 여러 서비스들을 가장 빠른 속도로 제공
- 글로벌 서비스 : 데이터 및 서비스를 전세계의 모든 인프라 공유
                 ex) CloudFront, IAM, Route53, WAF
- 지역 서비스 : 특정 리전을 기반으로 데이터 및 서비스 제공
               ex) 대부분의 서비스, S3(파일저장 서비스)

## IAM
* 글로벌 서비스 : 한번 만들면 AWS 전체의 적용
- 사용자 / 그룹 / 정책(policy) / 역할(Role)
- access control
- 허용 및 거부/관리
- 서비스 사용을 위한 인증정보 부여
- 사용자 생성 및 관리 및 계정의 보안
- 사용자의 패스워드 정책관리
- 다른계정과의 리소스 공유

* root 사용자 : 결제관리 포함한 계정의 모든 권한 가지고 있음
                관리 목적 외에 다른 용도로 사용하지 않는 것을 권장
                탈취 되었을때 복구가 매우 어려움 -> MFA 설정 권장
                MFA (Multi-factor authentication) : 일회용 패스워드 생성
* IAM 사용자 : IAM을 통해 생성해서 사용하는 사용자
               한 사람 혹은 하나의 어플리케이션을 의미
               설정 시 콘솔 로그인 권한 부여 가능
               설정 시 AWS 서비스 이용가능
* Access Key (user name)
* Secret Access Key (password) 

## JSON
- Java Script Object Notation
- 주로 다양한 프로그램 간에 데이터를 주고 받기 위해 사용
- 언어 자체에서 지원하거나 플로그인으로 사용 가능
- key - value 로 구성

## 가상화
- 하나의 컴퓨터를 여러 컴퓨터로 분할

운영체제(OS) : 시스템 하드웨어 자원과 소프트웨어 자원을 운영 관리
              ex) Windows, Linux ...
특권명령 : 시스템 요소들과 소통할 수 있는 명령 - OS 만 가능
           OS는 하나의 하드웨어 시스템당 하나밖에 들어갈 수 없음

## HVM (Hardware virtual Machine)
- 3세대 가상화
- 하드웨어에서 직접 가상화를 지원
- 직접 guest os가 하드웨어 와 통신 -> 빠른 속도 (near bare-metal)

## EC2 (Elastic Compare Cloud)
- 컴퓨터를 빌려주는 서비스
- 안전하고 크기 조정이 가능한 컴퓨팅 파워를 클라우드에서 제공하는 웹서비스
* 컴퓨팅을 빌려쓰는 서비스

. EC2 특성
 - 초 단위 온디맨드 가격모델
 - 빠른구축 속도와 확장성
 - 다양한 구성방법 지원
 - 여러 AWS 서비스와 연동

## EC2 구성
- 인스턴스 : 클라우드에서 사용하는 가상서버로 CPU, Memory, 그래픽카드 등 연산을 위한 H/W 담당
- EBS : Elastic Block Storage, 클라우드에서 사용하는 가상 하드디스크
- AMI : EC2 인스턴스를 실행하기 위한 정보를 담고 있는 이미지
- 보안그룹 : 가상의 방화벽

. 온디맨드 : 쓰는 만큼 비용 지불

.  EC2 인스턴스 : 컴퓨터 1대를 인스턴스라 함
                 ex) 컴퓨터 5대 필요하면 인스턴스 5개 만들면 됨

. EC2 : 독립적인 컴퓨터
        Linux, Window 운영체제 제공
        웹서버, 어플리케이션 서버로 사용

. S3 (Simple Storage Service)
 - 파일서버
 - 무제한으로 데이터 저장 가능
 - 스케일은 아마존 인프라 담당
 - 1byte ~ 5TB 단일 파일 저장 가능

. RDS (Relational Database Service)
 - 관계형 DB (MSSQL, NySQL, Oracle)
 - 백업, 리플리케이션을 아마존 인프라가 자동으로 제공

. ELB (Elastic Loab Balancing)
 - EC2로 유입되는 트래픽을 여러대의 EC2로 분산
 - 장애가 발생한 EC2를 감지해서 자동으로 배제
 - Auto Scaling 기능을 이용해서 EC2를 자동으로 생성, 삭제
