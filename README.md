# Backend Study

Java · Spring Boot · MySQL 기반 백엔드 개발을 단계별로 학습한 실습 저장소입니다.

---

## 기술 스택

![Java](https://img.shields.io/badge/Java_17-007396?style=flat&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot_3.3-6DB33F?style=flat&logo=springboot&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![H2](https://img.shields.io/badge/H2-0D6EFD?style=flat&logo=h2&logoColor=white)
![JPA](https://img.shields.io/badge/JPA/Hibernate-59666C?style=flat&logo=hibernate&logoColor=white)
![MyBatis](https://img.shields.io/badge/MyBatis-B50019?style=flat&logoColor=white)
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-005F0F?style=flat&logo=thymeleaf&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring_Security_6-6DB33F?style=flat&logo=springsecurity&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger/OpenAPI-85EA2D?style=flat&logo=swagger&logoColor=black)
![Socket.IO](https://img.shields.io/badge/Socket.IO-010101?style=flat&logo=socketdotio&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat&logo=gradle&logoColor=white)

---

## 프로젝트 구조

```
backend/
├── java/                  # Java 기초 문법 학습
│   └── JavaBasic/         # 타입, 연산자, 흐름제어, 클래스, 인터페이스, 람다, 제네릭
│
├── mysql/                 # SQL 학습 자료
│   └── README.md          # DQL·DDL·DML·DCL 전체 정리 및 예제
│
└── springboot/            # Spring Boot 실습 프로젝트
    ├── demo/              # Hello World — Spring Boot 기본 구조
    ├── demoex/            # 게시판 CRUD (JPA + H2 + Thymeleaf + Spring Security)
    ├── backend_1/         # REST API + Swagger + WebSocket 채팅 + 차트
    ├── demo_sc/           # Spring Security 인증·인가 데모
    ├── aop_test/          # AOP 및 Logback 로깅
    ├── test_mybatis/      # MyBatis + Maven 연동
    └── upload_test/       # 파일 업로드 (Ajax / Form)
```

---

## 실행 방법

각 프로젝트는 IntelliJ에서 독립적으로 열어서 실행합니다.

```bash
# 예시: demoex 프로젝트 실행
1. IntelliJ → File > Open → springboot/demoex 선택
2. build.gradle 인식 후 의존성 다운로드 대기
3. DemoexApplication.java 실행
4. http://localhost:8080 접속
```

> `backend_1`은 MySQL이 먼저 실행 중이어야 합니다.  
> `application.properties`에서 DB 접속 정보를 환경에 맞게 수정하세요.

---

## 학습 내용

| 폴더 | 주요 학습 내용 |
|------|---------------|
| `java` | 원시·참조 타입, 연산자, 흐름제어, OOP (상속·인터페이스), 람다, 제네릭 |
| `mysql` | SELECT·JOIN·서브쿼리, 집계함수, DDL(CREATE·ALTER·VIEW·INDEX), DML·DCL |
| `springboot/demo` | Spring Boot 프로젝트 구조, Controller, @ResponseBody |
| `springboot/demoex` | JPA CRUD, Thymeleaf 템플릿, Spring Security 세션 인증, 유효성 검사 |
| `springboot/backend_1` | REST API, Swagger UI, Socket.IO 실시간 채팅, Chart.js 연동 |
| `springboot/demo_sc` | Spring Security 설정, 커스텀 UserDetailService, 권한 정책 |
| `springboot/aop_test` | @Before·@After·@Around Aspect, Logback 로깅 |
| `springboot/test_mybatis` | Maven 빌드, MyBatis Mapper XML, BoardCRUD |
| `springboot/upload_test` | 단일·다중 파일 업로드, Ajax·Form 방식 처리 |

---

## 개발 환경

- **JDK 17** 이상 — [다운로드](https://download.oracle.com/java/17/archive/jdk-17.0.12_windows-x64_bin.exe)
- **IntelliJ IDEA** Ultimate (추천) / Community
- **Docker** — MySQL 컨테이너 실행

```bash
docker run -d -p 3306:3306 --name mysql \
  --env MYSQL_USER=ai \
  --env MYSQL_PASSWORD=1234 \
  --env MYSQL_ROOT_PASSWORD=1234 \
  mysql
```

- **DB 클라이언트** — HeidiSQL / MySQL Workbench / IntelliJ 내장 DB 탭
