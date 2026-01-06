# kubernetes-edu

본 저장소는 **오픈 클라우드 플랫폼 (K-PaaS) 전문가 교육 중,  
Container Platform 환경에 대한 이해를 높이기 위해 개인적으로 진행한 실습 프로젝트**입니다.

단순 과제 수행이 아니라,  
로컬 Minikube 환경에서 구성한 MSA 애플리케이션을  
실제 Kubernetes 클러스터(Container Platform) 환경으로 이전·배포해 보고자  
스스로 주제를 정해 진행하였습니다.

---

## 📌 프로젝트 목적

- 전문가 교육 과정에서 학습한 Kubernetes 개념을 실제 환경에 적용
- 로컬 Minikube 환경과 Container Platform 클러스터 환경의 차이 체감
- MSA 애플리케이션의 Kubernetes 배포 구조 이해
- MySQL 데이터 영속성(PV/PVC) 구성 경험
- 실무 환경에서의 서비스 운영 흐름 사전 학습

---

## 🧱 프로젝트 구성

본 프로젝트는 게시판, 댓글, 사용자, UI, API Gateway로 구성된  
**MSA 애플리케이션을 Kubernetes 환경에 배포하는 구조**로 설계되었습니다.
```
kubernetes-edu
├── Docker/                # 각 서비스 Docker 이미지 관련 파일
├── Kubernetes/            # Kubernetes 리소스(YAML) 정의
├── edu-msa-board          # 게시판 서비스
├── edu-msa-comment        # 댓글 서비스
├── edu-msa-user           # 사용자 서비스
├── edu-msa-ui             # 프론트엔드 UI
├── edu-msa-zuul           # API Gateway (Zuul)
└── README.md
```
---

## 🔄 주요 작업 내용

### 1. 실행 환경 전환
- 기존 **로컬 Minikube 환경**에서 실행되던 애플리케이션을  
  **Container Platform 기반 Kubernetes 클러스터 환경**으로 이전
- 클러스터 환경에 맞게 서비스, 네트워크 설정 반영

---

### 2. MySQL 설정 통합 및 초기화 구성
- 서비스별로 분리되어 있던 MySQL 설정 파일을 하나로 통합
- 컨테이너 실행 시 자동으로 테이블 및 기본 데이터가 생성되도록  
  **init SQL 스크립트 구성**

---

### 3. MSA 애플리케이션 배포
- 게시판, 댓글, 사용자, UI, API Gateway로 구성된  
  **MSA 애플리케이션을 Kubernetes 환경에 배포**
- 각 서비스 간 통신 구조 및 연계 방식 실습

---

### 4. MySQL PV / PVC 적용
- PersistentVolume(PV) 및 PersistentVolumeClaim(PVC) 구성
- Pod 재시작 또는 재배포 시에도 데이터가 유지되도록 스토리지 영속성 확보

---

## 🎯 학습 포인트

- Kubernetes 리소스 구성 및 배포 흐름 이해
- MSA 구조에서의 서비스 분리와 연계 방식
- 컨테이너 환경에서의 데이터베이스 운영 방식
- 로컬 환경과 클러스터 환경의 운영 차이점 이해

---

## 📎 참고

본 프로젝트는 **교육 및 실습 목적**으로 작성되었으며,  
Container Platform 기반 Kubernetes 환경에서  
MSA 애플리케이션을 배포·운영하는 전체 흐름을 경험하는 데 목적이 있습니다.
