# Dive Trip Project

## 1. Stack

+ [OpenJDK 17](https://openjdk.org/projects/jdk/17/)
+ [Spring Boot](https://spring.io/projects/spring-boot "Spring Boot")
+ [Spring Security](https://spring.io/projects/spring-security "Spring Security")
+ [Spring Data JPA](https://spring.io/projects/spring-data-jpa)
+ [Spring Data Redis](https://spring.io/projects/spring-data-redis)
+ [Spring Batch](https://spring.io/projects/spring-batch)
+ [Querydsl](http://www.querydsl.com/)
+ [Spring Test](http://docs.spring.io/spring-boot/docs/current/reference/html/boot-features-testing.html)
+ [Spring Security Test](http://docs.spring.io/spring-security/site/docs/current/reference/html/test-method.html)
+ [MariaDB](https://mariadb.org/ "MariaDB")
+ [Gradle Build Tool](https://gradle.org)
+ [Docker](https://www.docker.com)
+ [Logback](https://logback.qos.ch/)
+ [MapStruct](https://mapstruct.org/)
+ [JWT](https://jwt.io/)
+ [Apache Kafka](https://www.confluent.io/apache-kafka-vs-confluent/?utm_medium=sem&utm_source=google&utm_campaign=ch.sem_br.nonbrand_tp.prs_tgt.kafka_mt.xct_rgn.apac_lng.eng_dv.all_con.kafka-general&utm_term=kafka&creative=&device=c&placement=&gad_source=1&gclid=Cj0KCQiA7NO7BhDsARIsADg_hIb2NdtNoLW5Thz_h0SQtPAXKLRSiK-xCp-VsVbaD1LjBvzJ-UPWgu8aAusJEALw_wcB)

### Version 정보
+ java : `17`
+ gradle wrapper : `8.10`
+ spring boot(web, jpa, redis, security, validation, jdbc, devtools, test) : `3.3.7`
+ dependency-management-plugin : `1.1.0`
+ lombok : `1.16.14`
+ mapstruct : `1.5.5.Final`
+ querydsl : `5.0.0`
+ logback : `1.5.12`
+ jwt : `0.11.5`

## 2. Project 구성

### Gradle Multi Project
Build Tool은 [Gradle](https://gradle.org)을 이용 하며, Multi Project로 구성함으로써 Project Package를 재활용하여 중복되는 코드를 줄이고, Project를 계층 또는 다양화할 수 있도록 설계

### Project 구성
* [dive-trip](https://github.com/kbtapjm/dive-trip)
* [dive-trip-library](https://github.com/kbtapjm/dive-trip-library)
* [dive-trip-application](https://github.com/kbtapjm/dive-trip-application)
* [dive-trip-stream](https://github.com/kbtapjm/dive-trip-stream)
* [dive-trip-batch](https://github.com/kbtapjm/dive-trip-batch)

#### dive-trip
dive-trip 프로젝트의 `root project` (base gradle 설정을 포함)

#### dive-trip-library
dive-trip 프로젝트의 `library project`로 공통으로 사용하는 Entity, Repository, Utility 클래스를 정의

#### dive-trip-application
dive-trip 프로젝트의 `rest api project`로 연동에 필요한 API를 구현

* 인증 : `Spring Security Oauth2` 기반으로 구성하여 인증 하며, Token은 `JWT`방식을 이용
* API : `Spring Web`기반에 `@RestController`를 이용

#### dive-trip-stream
dive-trip 프로젝트의 `Message` 처리를 위한 `Reactive` 방식의 데이터 처리 Project

#### dive-trip-batch
dive-trip 프로젝트의 `Batch` 처리를 위한 Project