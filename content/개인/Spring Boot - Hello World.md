http://start.spring.io

Dependency는
- **Spring Web**
- **Spring Data JPA**
- **PostgreSQL Driver** (또는 H2 for 테스트)

### Layer
Request
- ⇒ Controller: `@RestControler`
- ⇒ Service: `@Service`
- ⇒ Repository: `@Repository`
- ⇒ DB

DB: Postgre
확인
```sh
netstat -ano | findstr 5432
```

Client 접속
```sh
psql -U postgres # LISETNING
```
- [[LISTENING]]

아닐 경우
```powershell
net start postgresql-x64-18
```

### 서버 실행
```sh
./gradlew bootrun
```

### HTTP Test

---
궁금
스킬업
- 더욱 복잡한 구조의 Spring 시스템은 어떨까? 복잡도는 다음과 같은 방식으로 올라간다:
	- 다양한 Exception을 처리하는 문제
	- 기능의 개수, 어떻게 서로를 참조하는지
- 해결하는 방법은
	- 모니터링: 로깅
	- 버전관리

