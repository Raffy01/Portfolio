# 엄우용 - Backend & System Programmer Portfolio

저는 숭실대학교 컴퓨터학부에서 수학하며 C 기반의 Linux POSIX 시스템 프로그래밍과 네트워크 소켓 통신에 깊은 전문성을 쌓았습니다. 
단순히 프레임워크를 사용하는 것을 넘어, **Raw Socket 수준의 패킷 제어**, **Custom TCP/IP 프로토콜 설계**, 그리고 
**TLS 기반의 안전한 서버 통신**을 직접 구현하며 시스템을 파악하는 데 노력을 쏟았습니다.

---

## Tech Stack

### Languages
![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Kotlin](https://img.shields.io/badge/kotlin-%237F52FF.svg?style=for-the-badge&logo=kotlin&logoColor=white)
![SQL](https://img.shields.io/badge/sql-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white)
![Bash](https://img.shields.io/badge/bash-%234EAA25.svg?style=for-the-badge&logo=gnu-bash&logoColor=white)

### System & Network
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![POSIX](https://img.shields.io/badge/POSIX_API-8E75B2?style=for-the-badge&logo=cplusplus&logoColor=white)
![Raw Sockets](https://img.shields.io/badge/Raw_Sockets-FF6C37?style=for-the-badge&logo=gnutls&logoColor=white)

### Backend & Infrastructure
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![EC2](https://img.shields.io/badge/Amazon_EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white)
![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white)
![OpenSSL](https://img.shields.io/badge/OpenSSL-721412?style=for-the-badge&logo=openssl&logoColor=white)
![GCP](https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=for-the-badge&logo=google-cloud&logoColor=white)

---

## Featured Projects

### 1. 네트워크 & 백엔드 아키텍처 (End-to-End & Cloud Ops)
표준 HTTP 프레임워크에 의존하지 않고, 직접 보안 소켓 통신 규격을 설계하여 실제 클라우드 환경에서 운영한 풀스택 프로젝트입니다.

* **[JJikEoVoCa Backend Server](https://github.com/Raffy01/JJikEoVoCa-Server)**
  * **Description:** 영어 단어장 어플리케이션을 위한 멀티스레드 기반 TCP/IP 소켓 서버
  * **Tech:** Python, OpenSSL, SQLite, **AWS (EC2, Elastic IP)**, Google Gemini API, GCP Vision/STT
  * **Key Contributions:**
    * **Cloud Deployment:** AWS EC2 인스턴스 환경에서 서버를 직접 배포하고 Elastic IP를 활용해 약 3개월간 안정적인 서비스 유지보수 수행
    * **Protocol Design:** OpenSSL 기반 TLS 암호화 통신 및 Custom 4-Byte Header JSON 프로토콜 설계/구현
    * **Optimization:** Thread-safe한 SQLite Connection Pool 구현 및 음성 데이터(STT) in-memory 인코딩 파이프라인 구축
    * **AI Integration:** RAG(Retrieval-Augmented Generation) 기반 AI 챗봇 통합

* **[JJikEoVoCa Android Network SDK](https://github.com/Raffy01/JJikEoVoCa-Network-SDK)**
  * **Description:** 커스텀 TCP/IP 백엔드 서버와 통신하기 위한 Android 클라이언트 네트워크 계층
  * **Tech:** Kotlin, Coroutines, kotlinx.serialization
  * **Key Contributions:**
    * Kotlin Coroutines를 활용한 비동기 I/O 처리 및 직렬화/역직렬화 파이프라인 구축
    * 멀티파트 파일(오디오, 이미지) 데이터의 안전한 스트림 전송 구현

### 2. 심화 네트워크 시스템 프로그래밍
* **[Nettool: 멀티스레드 네트워크 스캐너](https://github.com/Raffy01/nettool)**
  * **Description:** OS 네트워크 레이어를 우회하여 IP/TCP 헤더를 직접 조작하는 C 기반 고속 네트워크 정찰 도구
  * **Tech:** C, Linux Raw Sockets, Pthreads
  * **Key Contributions:**
    * POSIX Raw Socket을 활용한 ICMP Ping Sweep 및 Stealth TCP SYN Scan 구현
    * 비동기 패킷 송수신과 Pthreads를 통한 멀티스레딩으로 스캔 속도 극대화
    * TTL 및 TCP Window Size 분석을 통한 정밀한 타겟 OS 핑거프린팅 로직 작성

### 3. 리눅스 시스템 프로그래밍 스위트 (System Utilities)
리눅스 커널과 POSIX API의 깊은 이해를 바탕으로, 파일 시스템 제어와 프로세스 관리를 다루는 유틸리티입니다.

* **[Local Version Control System (repo)](https://github.com/Raffy01/Version-Control)**
  * `fork()`와 `execvp()`를 활용한 CLI 구축 및 LCS 알고리즘 기반의 파일 Diff 분석, 버전 커밋/롤백 구현
* **[Background Directory Sync Daemon](https://github.com/Raffy01/Background-Synchronization-Daemon)**
  * 터미널에서 분리된 백그라운드 데몬 프로세스 구현, MD5 해싱을 통한 실시간 파일 수정 감지 및 IPC(SIGUSR1) 제어
* **[Backup & Recovery Utility](https://github.com/Raffy01/Backup-Recovery)**
  * 재귀적 디렉토리 탐색(`scandir`), MD5 무결성 검증, 상호작용형 CLI(Tree 구조 시각화)를 통한 안전한 파일 백업/복구 시스템 구현

### 4. ⚙데이터 파이프라인 및 자동화
* **[C Feature Extraction Pipeline](https://github.com/Raffy01/C-Feature-Extraction-Pipeline)**
  * **Description:** C 소스 코드의 특징(CFG, 루프, 시스템 콜 등)을 병렬로 추출하는 자동화 파이프라인
  * **Tech:** Bash, Python, C, GCC Dumps, perf, strace
  * **Key Contributions:**
    * `perf`와 `strace`를 연동하여 하드웨어 이벤트 및 시스템 콜 동적 추적
    * 백그라운드 Job 제어(`wait`, `flock`)를 통한 멀티 프로세스 병렬 추출 최적화

---

## Education & Languages

* **학력:** 숭실대학교 컴퓨터학부 (학점: **4.16** / 4.5)
  * *운영체제, 네트워크, 시스템 프로그래밍 등 로우레벨 CS 기초 심화 학습 및 우수 성적 수료*
* **어학:** TOEIC **955**점 (2025.12 취득)
  * *영문 공식 기술 문서(Documentation) 독해 및 글로벌 레퍼런스 기반의 원활한 트러블슈팅 가능*

---

## Contact

* **Email:** [vo101021@gmail.com](mailto:[vo101021@gmail.com])
* **GitHub:** [https://github.com/Raffy01](https://github.com/Raffy01)
