# 프로젝트 명 : OnedayClass 
## 프로젝트 목표 : 데일리 강좌를 신청하고 이용할 수 있는 웹 서비스 제공
## 팀원 소개🧐
😎팀장 : 곽지현 - [깃허브](https://github.com/TsukinoHikari) / ☺️팀원 : 김동욱 - [깃허브](https://github.com/pier101) , 전진영 - [깃허브](https://github.com/jeonjinoung), 최현석 - [깃허브](https://github.com/Tozinoo)

## 프로젝트 기간 : 2021.09-29 ~ 2021.10.15 

# 목차
1. 개요
2. 목적
3. 디렉토리 구조
4. 사용기술
5. 주요기능
6. 발생이슈 & 해결과정
7. DB ERD
 

# 1. 개요

원데이클래스 제공 플랫폼


# 2. 목적 

> 원데이 클래스 제공 플랫폼
>   1. 프로젝트 구조 설계 경험
>   2. 노드 요청 처리에 대한 이해
>   3. 데이터베이스 관리

# 3. 디렉토리 구조

    OneDayClass
    |
    |--config       - 각종 환경 설정 관리 폴더
    |--models       - 데이터베이스 모델 모음 폴더
    |--node_modules - 모듈
    |--passport     - 세션 관리 폴더
    |--public       - 정적 파일 보관 폴더
    |   |--image    - 정적 이미지 파일 보관 폴더
    |--routes       - 각종 라우터 모음
    |--seeders      - seed 데이터 초기 값 관리 폴더
    |--uploads      - 사용자 업로드 이미지 관리 폴더
    |--views        - 템플릿 엔진 모음 폴더
    |
    |--app.js       - 진입 파일


# 4. 사용기술

-   웹 화면 구성 : `JavaScript`, `Nunjucks`, `HTML`, `CSS`
-   DB 액션 처리 : `Sequelize`
-   DBMS : `MySQL`
-   개발 Tool : `Visual Studio Code` `Git`
-   프레임워크 : `NodeJs` `Express`
-   결제: [BOOTPAY](https://www.bootpay.co.kr)
-   프로젝트 관리 Tool : `Google Drive` `GitHub`


사용 모듈 :  
 ```
   "bcrypt": "^5.0.1",  
   "cookie-parser": "^1.4.5",  
   "dotenv": "^10.0.0",  
   "express": "^4.17.1",  
   "express-session": "^1.17.2",  
   "express-validator": "^6.12.2",  
   "moment": "^2.29.1",  
   "morgan": "^1.10.0",  
   "multer": "^1.4.3",  
   "mysql2": "^2.3.0",  
   "nodemailer": "^6.6.5",  
   "nodemailer-smtp-transport": "^2.7.4",  
   "nunjucks": "^3.2.3",  
   "passport": "^0.5.0",  
   "passport-google": "^0.3.0",  
   "passport-google-oauth2": "^0.2.0",  
   "passport-kakao": "^1.0.1",  
   "passport-local": "^1.0.0",  
   "sequelize": "^6.7.0",  
   "sequelize-cli": "^6.2.0"
   ```
   


# 5. 주요기능

#### 메인페이지
    -   카테고리 구현, 검색, 슬라이드, 로그아웃
#### 회원가입 : 일반 유저 회원가입
    -   유효성 검사,  중복확인
#### 로그인 : 사용자의 일반, SNS 로그인 분리
    -   일반 로그인, SNS 로그인, 아이디/비밀번호 찾기
#### 클래스 등록
    -   이미지 업로드
#### 클래스 상세보기
    -   상품 상세보기, 찜하기, 댓글, 장바구니 담기
#### 장바구니
    -   장바구니 목록 삭제, 결제
#### 마이페이지
    -   회원정보 수정, 찜목록 띄우기, 결제한 클래스 내역, 장바구니 목록
#### 게시판 : 일반 유저와 관리자 접근 권한 분리
    -   일반 게시판, 관리자 게시판




# 6. 발생이슈 & 해결 과정

### "passport 2개 연결"

-  passport missing credentials 오류

[상황] 일반 유저, 관리자 분리하여 작업 후 passport 연결

[문제] 로그인 시 missing credentilas 오류 발생

[해결] 일반 유저 로그인 시 관리자 부분 주석 처리. (보완 필요)

### "Nunjucks 사용 미숙"

-  nunjucks 사용 처음

[상황] 처음에 블럭을 만들지 않고 사용

[문제] 코드 병합 시 엇갈리는 부분 발생

[해결] 블럭을 만들어서 헤드 푸터 부분 획일화 및 중복되는 부분 제거

### "DB 저장 시간"

[상황] mysql db로 데이터 저장 

[문제] 데이터 저장 시 현재 시간으로 저장 되지 않음

[해결] UTC 시간으로 저장되므로 설정에 timezone +09:00(한국) 설정

### "Sequelize문법 사용"

[상황] Sequelize 문법을 사용해서 테이블 간 조인

[문제] 테이블 조인 시 기존 SQL문법이 더 편함

[해결] QueryTypes 사용하여 SQL문법 바로 사용


# 7. DB ERD

![onedayclass_db](https://user-images.githubusercontent.com/85658044/143537708-582d1548-8542-478e-8a95-80069c71f283.png)

