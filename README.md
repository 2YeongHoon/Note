# [Server] Name

![Java](https://img.shields.io/badge/Java-11-red.svg)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-2.7.0-green.svg)
![Hibernate](https://img.shields.io/badge/Hibernate-5.6.9-orange.svg)
![MySql](https://img.shields.io/badge/MySql-8.0.29-blueviolet.svg)
![Gradle](https://img.shields.io/badge/Gradle-7.4.1-yellow.svg)
![Swagger](https://img.shields.io/badge/Swagger-3-blue.svg)
![Lombok](https://img.shields.io/badge/Lombok-1.18.14-lightgray.svg)
![Guava](https://img.shields.io/badge/Guava-31.1-lightgray.svg)
![QueryDsl](https://img.shields.io/badge/QueryDsl-5.0.0-lightgray.svg)

2022/09/29

# Branch
기본적으로 git-flow 전략을 따릅니다.
```
- `master`: 기준이 되는 브랜치로 제품을 배포하는 브랜치 입니다.
 
- `develop`: 개발 브랜치로 개발자들이 이 브랜치를 기준으로 각자 작업한 기능들을 합칩니다(Merge).
 
- `feature/`: 단위 기능을 개발하는 브랜치로 기능 개발이 완료되면 develop 브랜치에 합칩니다.
  - `default`: 단위 기능 개발을 위한 최소한의 의존성을 제공하는 브랜치 입니다. 패키지 의존성 추가가 있는 경우만 해당 브랜치의 빌드 관리 도구에 Update 합니다. 이 브랜치는 제거되지 않습니다.
  - `${taskNum}_${featureName}`: 네이밍 규칙은 지라 티켓의 번호_신규 개발 기능의 명칭으로 생성합니다. 기능 개발 완료 후 develop 에 병합 후 제거됩니다.
    
- `release/`: 배포를 위해 master 브랜치로 보내기 전에 먼저 QA(품질검사)를 하기위한 브랜치 입니다.
  - `${releaseVersion}`: 네이밍 규칙은 릴리즈 버전에 맞추어 생성합니다. 검수 완료되면 tagging 후 제거됩니다.
    
- `hotfix/`: master 브랜치로 배포를 했는데 버그가 생겼을 떄 긴급 수정하는 브랜치 입니다.
  - `${issueNum}`: 네이밍 규칙은 지라 티켓의 번호로 생성합니다. master 반영 후 제거됩니다.
  
# Commit Rules
```
NEW: 신규 파일 및 기능 추가
IMP: 기능 개선
SCH: 설정 변경
CLN: 코드 정리 및 리팩토링
BUG: 버그 픽스
TST: 테스트
DOC: 문서작업
RMV: 삭제

ex) NEW: 사용자 서비스 추가
```


# Directory Structure
추후 작성

# Reference

- [Spring Boot](https://spring.io/projects/spring-boot)
- [Gradle](https://docs.gradle.org/current/userguide/userguide.html)
- [Jasypt Converter](https://www.devglan.com/online-tools/jasypt-online-encryption-decryption)

---

# 개발표준 정의

## 개요
프로젝트의 개발 시 개발생산성 향상 및 운영의 효율화를 위해 반드시 준수되어야 하는 준수사항을 정의함

- 제시된 표준은 철저히 준수한다.
- 모든 거래 최대 응답속도 5초 이내를 목표로 구현되어야 한다.
- 본 표준안은 최소한의 필수사항을 지키도록 유도하고 해서는 안되는 것들을 지적하는 내용이며, 개개인의 다양한 능력과 개념들로 본 표준을 확장시켜 시스템에 적용시키도록 한다.

## 명명규칙

작성중

## 주석
- 각 Method 앞에 Method의 Parameter, Return Value의 의미와 Method의 간략한 설명을 기술한다.
- 해당 프로그램의 핵심적인 중요 로직에 대해서는 반드시 그에 따른 주석을 추가한다.
- 사용하지 않는 로직이라면 지우고 사용 예정이라 주석처리를 했다면 반드시 TODO를 작성한다.
- JavaDoc을 표준을 준수하며, 이용하여 프로그램 사양서를 작성할 수 있도록 한다.

예 )
```
    /**
     * 거래 시작 핸들러
     *
     * @param request 요청 데이터
     * @param response 응답 데이터
     * @param handler 핸들러
     *
     * @return 항상 참
     * @exception Exception 예외
     */
    @Override
    public boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler) throws Exception {
        ...
    }
```
