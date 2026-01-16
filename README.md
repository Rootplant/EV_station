# ⚡ EV Station — 전기차 충전소 정보 & 실시간 예약/고장신고 플랫폼

<p align="center">
  <img src="https://github.com/user-attachments/assets/328961d9-b838-410d-801d-c171ee94bcd0" alt="EV Station Project Banner" />
</p>

## 📌 프로젝트 소개
**EV Station**은 실시간 전기차 충전소 정보, 예약, 결제, 고장 신고 등  
전기차 운전자에게 꼭 필요한 기능을 제공하는 **충전소 통합 정보 플랫폼**입니다.  

공공데이터 기반 충전소 API와 지도 API를 연동하여  
**충전소 위치, 충전기 상태, 현재 혼잡도 정보를 지도 중심으로 직관적으로 제공**하며,  
Redis 캐싱을 활용해 대규모 데이터 환경에서도 안정적인 성능을 유지하도록 설계되었습니다.

---

## 👨‍💻 담당 역할 (정찬호)

> **지도 기반 실시간 충전소 서비스 핵심 기능 담당**

| 구분 | 담당 내용 |
|---|---|
| 🗺 지도 서비스 | 카카오 지도 API 연동, 충전소 마커 표시 및 클러스터링 |
| 🔌 충전소 API | 공공데이터 충전소 API 연동 및 실시간 데이터 가공 |
| 📊 상태/혼잡도 | 충전기 상태(사용중/사용가능/점검중) 기반 현재 혼잡도 산출 |
| 🔍 검색 기능 | 충전소명 / 지역 기반 검색 시스템 구현 |
| ⭐ 즐겨찾기 | 사용자별 충전소 즐겨찾기 기능 |
| 📄 상세 페이지 | 충전소 상세 정보 페이지 구현 |
| ⚡ 성능 최적화 | Redis 캐싱 적용, API·DB 부하 감소 |
| 🧱 DB 설계 | 충전소·상태·즐겨찾기 관련 DB 구조 설계 |
| 🎨 UI / UX | 지도 중심 화면 흐름 개선 |
| 🛠 유지보수 | 지도·데이터 불일치 버그 수정 |

---

## ✨ 주요 기능

- 🔐 **회원 관리**
  - 회원가입, 로그인/로그아웃, 마이페이지
  - Spring Security 기반 비밀번호 암호화

- 🗺 **지도 기반 충전소 검색**
  - 충전소 위치 마커 및 클러스터링
  - 지도 이동/확대·축소 시 동적 렌더링

- 🔌 **공공데이터 기반 실시간 충전소 정보**
  - 충전기 상태 실시간 반영
  - 데이터 가공 후 UI 표시

- 📊 **충전기 상태 기반 현재 혼잡도 제공**
  - 사용중/가용 충전기 비율 기반 혼잡도 계산

- 🔍 **검색 & 즐겨찾기**
  - 충전소 검색
  - 즐겨찾기 등록 및 빠른 접근

- 📄 **충전소 상세 페이지**
  - 충전소 위치, 상태, 혼잡도, 주변 정보 제공

- 🛠 **고장 신고 & 관리자 처리**

- 💳 **예약 / 결제**
  - 충전소 예약
  - 토스 API 기반 결제

- 🧑‍💼 **관리자 페이지**
  - 회원 관리, 고장 처리, 예약 관리

- ⚡ **Redis 기반 성능 최적화**
  - 빈번한 충전소 데이터 캐싱
  - 공공 API 호출 횟수 감소

---
## 🔍 내가 구현한 핵심 기능

---

### 🗺 지도 기반 충전소 조회 & 클러스터링

<p align="center">
  <img src="https://github.com/user-attachments/assets/8b715763-2b49-49f3-a6de-0683423251e6" width="45%" />
  <img src="https://github.com/user-attachments/assets/cfea937d-6b08-47fd-ae7b-d693a38789f6" width="45%" />
</p>

📌 **설명**

- 카카오 지도 API 연동
- 충전소 좌표 기반 마커 표시
- 지도 확대/축소 시 클러스터링 적용
- 지도 이동 이벤트에 따른 동적 데이터 렌더링

👉 대규모 충전소 데이터 환경에서도  
지도 성능 저하 없이 안정적인 사용자 경험 제공

---

### 🔌 충전기 상태 기반 실시간 혼잡도 산출

<p align="center">
  <img src="https://github.com/user-attachments/assets/fa0737e6-127a-4f82-b01f-682251937838" width="90%" />
</p>

📌 **설명**

- 공공데이터 충전기 상태 코드 가공
- 사용중 / 사용가능 / 점검중 상태 분류
- 가용 충전기 비율 기반 혼잡도 계산
- 지도 및 상세 페이지 UI에 즉시 반영

👉 단순 상태 조회가 아닌  
**사용자 체감 혼잡도 정보 제공**

---

### 🔍 충전소 검색 & 즐겨찾기

<p align="center">
  <img src="https://github.com/user-attachments/assets/1fbabf0e-5bc3-408a-98c5-d43b5bf8a231" width="45%" />
  <img src="https://github.com/user-attachments/assets/9289147a-63b1-4987-95aa-7761576fc0a9" width="45%" />
</p>

📌 **설명**

- 충전소명 / 지역 기반 검색 기능
- 사용자별 즐겨찾기 등록
- 즐겨찾기 충전소 빠른 접근 제공

---

### 📄 충전소 상세 페이지

<p align="center">
  <img src="https://github.com/user-attachments/assets/473b715763-2b49-49f3-a6de-0683423251e6" width="45%" />
</p>

📌 **설명**

- 충전소 위치, 충전기 목록 제공
- 상태·혼잡도 정보 통합 표시
- 지도 → 상세 페이지 자연스러운 사용자 흐름 구성

---

### ⚡ Redis 기반 성능 최적화

📌 **설명**

- 충전소 기본 정보 및 상태 데이터 Redis 캐싱
- 공공 API 호출 횟수 감소
- 지도 이동·검색 시 DB 부하 최소화
- 다수 사용자 접근 환경에서도 안정적인 응답 속도 유지

---

## 📸 서비스 화면 예시

### 🔐 로그인 / 🧾 회원가입
<p align="center">
  <img src="https://github.com/user-attachments/assets/305dc810-6546-4b67-b403-b15eb5d3e120" width="47%" />
  <img src="https://github.com/user-attachments/assets/90d3a052-07a2-495f-82f5-eb90cdf1168e" width="47%" />
</p>

---

### ⚡ 충전소 지도 / 혼잡도 예측
<p align="center">
  <img width="1915" height="913" src="https://github.com/user-attachments/assets/fa0737e6-127a-4f82-b01f-682251937838" />
</p>

<p align="center">
  <img width="473" height="476" src="https://github.com/user-attachments/assets/8b715763-2b49-49f3-a6de-0683423251e6" />
  <img width="512" height="434" src="https://github.com/user-attachments/assets/cfea937d-6b08-47fd-ae7b-d693a38789f6" />
</p>

<p align="center">
  <img width="237" height="374" src="https://github.com/user-attachments/assets/1fbabf0e-5bc3-408a-98c5-d43b5bf8a231" />
  <img width="253" height="443" src="https://github.com/user-attachments/assets/9289147a-63b1-4987-95aa-7761576fc0a9" />
</p>

---

### 🛠 고장신고 / 관리자 고장처리
<p align="center">
  <img src="https://github.com/user-attachments/assets/61e75082-d0f4-4c17-9fcd-16fbbc52f89a" width="47%" />
  <img src="https://github.com/user-attachments/assets/da23acb3-0335-47c6-a022-182a8a923cc3" width="47%" />
</p>

---

### 📢 공지사항 / 자유게시판
<p align="center">
  <img src="https://github.com/user-attachments/assets/56ea9b5c-9e2c-4dae-9eed-633dfb8eac61" width="47%" />
  <img src="https://github.com/user-attachments/assets/cca601d6-b109-4a06-94ed-b90c4a7c3706" width="47%" />
</p>

---

### 💳 예약 결제 / 결제 성공·실패
<p align="center">
  <img src="https://github.com/user-attachments/assets/e0f450e5-937a-435b-a47e-69e63e8c48bd" width="47%" />
  <img src="https://github.com/user-attachments/assets/d8c274cc-74f1-47a9-bf54-ea16b38c7700" width="47%" />
</p>

---

### 👤 마이페이지 / 관리자 회원관리
<p align="center">
  <img src="https://github.com/user-attachments/assets/8c9e4469-43c5-4df4-9475-a9d9c3d0fb54" width="47%" />
  <img src="https://github.com/user-attachments/assets/1f9b3dd5-9179-4d13-8854-d83097329722" width="47%" />
</p>

---

### 🔐 아이디 & 비밀번호 찾기
<p align="center">
  <img src="https://github.com/user-attachments/assets/9c259fdd-88e4-46de-b179-c8dd4115f04c" width="47%" />
  <img src="https://github.com/user-attachments/assets/c492c839-aa1f-4229-bd1c-355af70a325c" width="47%" />
</p>

---

## 🛠 기술 스택

### Backend
- Java 17
- Spring Framework / MVC / Security
- MyBatis
- Tomcat
- Oracle Database
- Redis

### Frontend
- JSP
- HTML5 / CSS3 / JavaScript
- jQuery

### Tools
- Git / GitHub
- Gradle
- Postman

---

## 💡 한 줄 요약

> **공공데이터 기반 충전소 API와 지도 서비스를 연동하고,  
충전기 상태·혼잡도를 실시간으로 가공하여 Redis로 성능을 최적화한  
지도 중심 전기차 충전소 플랫폼**
