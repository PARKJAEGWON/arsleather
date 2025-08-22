# arsleather 개인 프로젝트

https://arsleatherkorea.com/
테스트용 계정 아이디 groo 비밀번호 a12345678
# ARS Leather Korea 🛍️

쇼핑몰 프로젝트입니다.

## 🛠 사용 기술

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

## 📋 ERD

<img width="1069" height="630" alt="erd" src="https://github.com/user-attachments/assets/3fe34455-3872-4612-b8f5-f010e23836ed" />

## 💡 주요 기능

### 1. 회원 관리
- JWT 기반 인증
- 회원가입/로그인/탈퇴
  - 이메일, 아이디 중복 검사 JPA existsBy를 사용하여 존재하는 여부를 확인 후 서비스로직에서 중복 검사
  - 아이디 찾기: 이름, 생년월일, 가입 시 기재했던 이메일을 입력하여 뒤 3자를 마스킹 처리해 알려줌
  - 비밀번호 찾기: 이름, 아이디, 가입 시 기재했던 이메일을 입력하여 재설정
  - 비밀번호 암호화 (BCrypt)
- 회원 탈퇴 자동화 (스케줄러)
  - 탈퇴 신청 회원 상태가 8 로 변경 8 상태로 14일 후 자동 삭제(DB에서 회원정보 제거) 14일 이내 로그인 시 복구 알림창이 나오고 확인시 회원 상태 0으로 변경하여 복구

### 2. 주문/결제
- 토스페이먼츠 결제 연동
  - 결제 준비/승인 프로세스
  - 카드 결제 정보 관리
- 주문 상태 관리
  - 배송준비중/배송중/배송완료/구매확정
  - 반품처리/주문취소 프로세스

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
