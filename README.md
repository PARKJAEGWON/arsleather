# 개인 프로젝트

https://arsleatherkorea.com/
# 테스트용 계정 
아이디 groo 비밀번호 a12345678
<br>비밀번호 변경 테스트 시 비밀번호 원상복구 부탁드립니다.
# ARS Leather Korea 🛍️

<img width="1211" height="671" alt="개요" src="https://github.com/user-attachments/assets/28494db9-267f-45e1-9789-51e54d51f632" />


## 사용 기술

### Backend
- Java 21
- Spring Boot 3.4.5
- Spring Security + JWT
- Spring Data JPA
- MySQL

### Frontend
- JSP
- JavaScript
- CSS

### DevOps
- Terraform: AWS EC2 인프라 프로비저닝 및 설정
- Docker: 애플리케이션 컨테이너라이제이션 및 이미지 기반 배포

### Deployment
- AWS EC2: Terraform으로 프로비저닝된 인스턴스에 Docker 컨테이너 직접 배포

### 개발 보조 도구
- Cursor AI

## ERD

<img width="1069" height="630" alt="erd" src="https://github.com/user-attachments/assets/3fe34455-3872-4612-b8f5-f010e23836ed" />

## 아키텍처

<img width="1230" height="690" alt="시스템 아키텍처" src="https://github.com/user-attachments/assets/2805746a-c0af-4887-be0c-8af17bb27b96" />


## CI / CD 파이프라인

<img width="1221" height="678" alt="ci 아키텍처" src="https://github.com/user-attachments/assets/11d1c5b4-67a3-4abd-b89c-95d8eff14abb" />


## 주요 기능

### 1. 회원 관리
- JWT 기반 인증
- 회원가입/로그인/탈퇴
  - 이메일, 아이디 중복 검사 JPA existsBy를 사용하여 존재하는 여부를 확인 후 서비스로직에서 중복 검사
  - 아이디 찾기: 이름, 생년월일, 가입 시 기재했던 이메일을 입력하여 뒤 3자를 마스킹 처리해 알려줌
  - 비밀번호 찾기: 이름, 아이디, 가입 시 기재했던 이메일을 입력하여 재설정
  - 비밀번호 암호화 (BCrypt)
- 회원 탈퇴 자동화 (스케줄러)
  - 탈퇴 신청 시 회원 상태가 8로 변경되며, 8 상태로 14일 후 자동 삭제(DB에서 회원 정보 제거), 14일 이내 로그인 시 복구 알림창이 나오고 <br>확인 시 회원 상태가 0으로 변경되어 복구됨
<img width="1225" height="677" alt="로그인" src="https://github.com/user-attachments/assets/2a0e3131-1889-461b-9674-7948827fb907" />
<img width="1220" height="681" alt="로그인 2" src="https://github.com/user-attachments/assets/33664852-6b08-4fcf-a653-cdbb2c56454e" />


### 2. 결제/주문
- 카드 결제 프로세스 
  - js에서 임시 주문번호 생성하여 토스 페이먼츠 결제창 호출 및 결제 정보 전달 결제 성공 시 서버에서 실제 주문번호 생성 결제정보와 주문 정보 <br>연동 처리
- 무통장 입금
  - 주문 생성시 입금자명 저장 실제 주문번호 즉시 생성
- 주문 상태 관리
  - 배송준비중/배송중/배송완료/구매확정/반품처리/주문취소
<img width="1220" height="685" alt="W" src="https://github.com/user-attachments/assets/6ff8b060-5084-43dc-8a80-1ed87c09f3a4" />
<img width="1221" height="689" alt="결제" src="https://github.com/user-attachments/assets/8295d3e9-795a-4dbd-8d01-9a288f5806aa" />

### 3. 관리자 기능
- 회원 관리
  - 회원 목록/상세 조회
  - 회원 상태 관리
- 주문 관리
  - 주문 상태 변경
  - 배송 정보 관리
- 상품 관리
  - 상품 CRUD
  - 이미지 업로드
<img width="1232" height="683" alt="1AS" src="https://github.com/user-attachments/assets/3c4ff672-9ec8-4176-9abb-a2ffa81ff592" />
<img width="1220" height="680" alt="5959" src="https://github.com/user-attachments/assets/c7d44147-c627-44e5-8947-af0b38d7b386" />

## 트러블 슈팅

<img width="1229" height="685" alt="트1" src="https://github.com/user-attachments/assets/9e8e7fc1-f5b9-49eb-8543-6004a16b779c" />

<img width="1229" height="682" alt="트2" src="https://github.com/user-attachments/assets/26ff3873-840c-45df-b130-e0077418859f" />

<img width="1223" height="682" alt="트3" src="https://github.com/user-attachments/assets/7b1290ac-55a4-4c87-a123-546aaa68d8ff" />

