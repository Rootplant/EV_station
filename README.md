# ⚡ EV Station — 전기차 충전소 정보 & 실시간 예약/고장신고 플랫폼

<p align="center">
  <img src="https://github.com/user-attachments/assets/328961d9-b838-410d-801d-c171ee94bcd0" alt="EV Station Project Banner" />
</p>

## 📌 프로젝트 소개
**EV Station**은 실시간 전기차 충전소 정보, 예약, 결제, 고장 신고 등  
전기차 운전자에게 꼭 필요한 기능을 제공하는 **충전소 통합 정보 플랫폼**입니다.  
Spring, JSP, Oracle DB, MyBatis, Spring Security 및 공공데이터 API 연동을 통해  
**지도 기반 실시간 충전소 상태와 혼잡도 정보를 직관적으로 제공**합니다.

---

## 👨‍💻 담당 역할 (정찬호)

> **지도 기반 실시간 충전소 서비스 핵심 기능 담당**

| 구분 | 담당 내용 |
|---|---|
| 🗺 지도 기반 서비스 | **카카오 지도 API 연동**, 충전소 위치 시각화, 마커·클러스터 처리 |
| 🔌 충전소 API 연동 | **공공데이터 충전소 API 연동**, 실시간 상태 데이터 가공 |
| 📊 실시간 상태 처리 | 충전기 **사용중 / 사용가능 / 점검중** 상태 반영, 현재 혼잡도 산출 |
| 🔍 검색 시스템 | 충전소명 / 지역 기반 **검색 시스템 구현** |
| ⭐ 즐겨찾기 | 사용자별 **충전소 즐겨찾기 기능** 구현 |
| 📄 상세 페이지 | **충전소 상세 정보 페이지 구현** (상태, 위치, 주변 정보) |
| ⚡ 성능 최적화 | **Redis 캐싱 적용**, 과도한 API 호출 및 DB 부하 감소 |
| 🧱 DB 설계 | 충전소·상태·예약·즐겨찾기 관련 **DB 구조 설계 및 연동** |
| 🎨 UI / UX | 지도 중심 UI 개선, 사용자 동선 고려한 화면 구조 개선 |
| 🛠 유지보수 | 지도 렌더링/데이터 불일치 이슈 **버그 수정 및 안정화** |

---

## ✨ 주요 기능

- 🔐 **회원 관리**
  - 회원가입, 로그인/로그아웃, 마이페이지
  - Spring Security 기반 비밀번호 암호화

- 🗺 **지도 기반 충전소 검색 서비스**
  - 카카오 지도 API 연동
  - 충전소 위치 마커 표시 및 **클러스터링 처리**
  - 지도 이동/확대·축소에 따른 동적 마커 렌더링

- 🔌 **공공데이터 기반 충전소 실시간 정보 연동**
  - 충전기 상태(사용중 / 사용가능 / 점검중) 실시간 반영
  - API 데이터 가공 후 화면 표시

- 📊 **충전기 상태 기반 현재 혼잡도 예측**
  - 충전기 가동 상태를 기준으로 **현재 혼잡도 산출**
  - 사용자에게 직관적인 혼잡도 지표 제공

- 🔍 **충전소 검색 시스템**
  - 충전소명 / 지역 기반 검색
  - 지도 화면과 검색 결과 동기화

- ⭐ **충전소 즐겨찾기 기능**
  - 사용자별 즐겨찾기 등록/해제
  - 마이페이지 및 지도 화면에서 빠른 접근 제공

- 📄 **충전소 상세 페이지**
  - 충전소 위치, 충전기 정보, 현재 상태, 혼잡도 정보 제공
  - 지도 ↔ 상세 페이지 자연스러운 이동 흐름 구성

- 🛠 **고장 신고 & 처리**
  - 회원 고장 신고 등록
  - 관리자 처리 및 상태 관리

- 💳 **예약 / 결제 기능**
  - 충전소 예약
  - 토스 API 기반 예약금 결제

- 🧑‍💼 **관리자 페이지**
  - 회원 관리, 고장 처리, 예약 내역 관리

- ⚡ **Redis 기반 성능 최적화**
  - 빈번히 조회되는 충전소/상태 데이터 캐싱
  - 공공 API 호출 횟수 감소
  - 다수 사용자 동시 접속 시 안정적인 응답 유지

- 🎨 **지도 중심 UI / UX 개선**
  - 사용자 이동 동선 최소화
  - 지도, 검색, 상세 정보 간 일관된 UX 제공

---

## 📸 서비스 화면 예시

### 🔐 로그인 / 🧾 회원가입
<p align="center">
  <img src="https://github.com/user-attachments/assets/305dc810-6546-4b67-b403-b15eb5d3e120" width="47%" />
  <img src="https://github.com/user-attachments/assets/90d3a052-07a2-495f-82f5-eb90cdf1168e" width="47%" />
</p>

### ⚡ 충전소 지도 / 혼잡도 예측
<p align="center">
  <img src="https://github.com/user-attachments/assets/8b715763-2b49-49f3-a6de-0683423251e6" width="47%" />
  <img src="https://github.com/user-attachments/assets/cfea937d-6b08-47fd-ae7b-d693a38789f6" width="47%" />
</p>

### 🛠 고장신고 / 관리자 고장처리
<p align="center">
  <img src="https://github.com/user-attachments/assets/61e75082-d0f4-4c17-9fcd-16fbbc52f89a" width="47%" />
  <img src="https://github.com/user-attachments/assets/da23acb3-0335-47c6-a022-182a8a923cc3" width="47%" />
</p>

---

## 🛠 기술 스택

### Backend
- Java 17
- Spring Framework / MVC / Security
- MyBatis
- Tomcat
- Oracle Database
- Redis (Caching & Session Management)

### Frontend
- JSP
- HTML5, CSS3, JavaScript
- jQuery

### DevOps & Tools
- Git / GitHub
- Gradle
- Postman

---

## 📁 프로젝트 폴더 구조

```plaintext
Charging_station/
├─ src/main/java/com.boot/
│  ├─ Board/
│  ├─ common.dto/
│  ├─ fix/
│  ├─ login/
│  ├─ Main_Page/
│  ├─ MY_Page/
│  ├─ Notice/
│  ├─ Reservation/
│  ├─ CacheConfig.java
│  └─ ChargingStationApplication.java
│
├─ src/main/resources/
│  └─ ...
│
├─ src/main/webapp/
│  └─ WEB-INF/views/
│     ├─ board/
│     ├─ common/
│     ├─ fix/
│     ├─ login_page/
│     ├─ my_page/
│     └─ notice/
│
├─ build.gradle
├─ gradlew
├─ gradlew.bat
├─ dummy_data.sql
└─ settings.gradle
