# Backend 학습 저장소

Java · Spring Boot · MySQL · MongoDB 기반 백엔드 학습 자료 및 실습 프로젝트 모음

---

## 기술 스택

| 분류 | 기술 |
|------|------|
| Language | Java 17 |
| Framework | Spring Boot 3.3.3 |
| Database | MySQL (Docker), H2 (개발용) |
| ORM | JPA / Hibernate, MyBatis |
| View | Thymeleaf, AdminLTE |
| Auth | Spring Security 6.x |
| API Docs | Swagger / SpringDoc OpenAPI 2.2.0 |
| Realtime | Socket.IO (netty-socketio 2.0.11) |
| Build | Gradle |
| Etc | Lombok, CORS |

---

## 폴더 구조

```
backend/
├── java/               # Java 기초 문법 학습
│   └── JavaBasic/      # 타입, 연산자, 흐름제어, 클래스, 인터페이스, 람다, 제네릭
├── mysql/              # SQL 학습 자료
│   └── README.md       # DQL·DDL·DML·DCL 전체 정리 및 예제
└── springboot/         # Spring Boot 실습 프로젝트
    ├── demo/           # Hello World – Spring Boot 기본 구조
    ├── demoex/         # 게시판 CRUD (JPA + H2 + Thymeleaf + Spring Security)
    ├── backend_1/      # REST API + Swagger + WebSocket 채팅 + 차트
    ├── demo_sc/        # Spring Security 인증·인가 데모
    ├── aop_test/       # AOP 및 Logback 로깅
    ├── test_mybatis/   # MyBatis + Maven 연동
    └── upload_test/    # 파일 업로드 (Ajax / Form)
```

---

## 프로젝트별 설명

### `demoex` – 게시판 CRUD
- Post(게시글) / Review(댓글) 1:N 관계
- JPA Entity → Repository → Service → Controller 플로우
- Thymeleaf + AdminLTE UI 템플릿
- Spring Security 세션 기반 로그인·로그아웃
- 입력 유효성 검사 (PostForm, ReviewForm)
- H2 내장 DB 사용 → `http://localhost:8080/h2-console`

### `backend_1` – REST API 서버
- MySQL 연동 Sales 데이터 집계 API (`GET /api/sales`)
- Swagger UI → `http://localhost:8080/swagger-ui/index.html`
- Socket.IO 기반 실시간 채팅 (netty-socketio)
- Chart.js 연동 차트 화면
- CORS 설정 포함 (React/Vue 연동 대비)

### `demo_sc` – Spring Security 데모
- 회원가입 / 로그인 / 로그아웃
- `AppSecurityConfig` 기반 URL 접근 정책
- `UserDetailService` 커스텀 인증 처리
- `AuthUtil` 컴포넌트 DI

### `aop_test` – AOP 로깅
- `@Before`, `@After`, `@Around` Aspect 예제
- Logback 설정 (`logback-spring.xml`)

### `test_mybatis` – MyBatis 연동
- Maven(`pom.xml`) 기반 빌드
- BoardMapper XML 방식 SQL 관리

### `upload_test` – 파일 업로드
- HTML Form 방식 / Ajax 방식 파일 업로드
- `FileUploadResultDto` 응답 구조

---

## 환경 구성

### JDK 설치
```bash
# 버전 확인
java -version   # 17 이상 필요
```
- 다운로드: https://download.oracle.com/java/17/archive/jdk-17.0.12_windows-x64_bin.exe

### IDE
- IntelliJ IDEA Ultimate (추천) / Community

### MySQL – Docker로 실행
```bash
docker run -d -p 3306:3306 --name mysql \
  --env MYSQL_USER=ai \
  --env MYSQL_PASSWORD=1234 \
  --env MYSQL_ROOT_PASSWORD=1234 \
  mysql
```

### DB 클라이언트
- HeidiSQL: https://www.heidisql.com/download.php
- MySQL Workbench: https://dev.mysql.com/downloads/workbench/
- 또는 IntelliJ 내장 DB 탭 / VS Code MySQL 익스텐션 (Weijan Chen)

---

## 실행 방법

각 프로젝트는 IntelliJ에서 독립적으로 열어서 실행합니다.

```
# 예시: demoex 프로젝트 실행
1. IntelliJ → File > Open → springboot/demoex 선택
2. build.gradle 인식 후 의존성 다운로드 대기
3. DemoexApplication.java 실행
4. http://localhost:8080 접속
```

`backend_1`은 MySQL이 먼저 실행 중이어야 합니다.  
`application.properties`에서 DB 접속 정보를 환경에 맞게 수정하세요.

---

## 원격 저장소 설정

```bash
git clone git@github.com:edu2ucoc/backend.git
```
