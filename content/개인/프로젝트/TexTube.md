
prisma cli가 뭐야?
여기서 실행하는 prisma야?

dependencies
devDependencies


prisma migrate deploy

DB가 존재하지 않기 때문이다.

[Railway에서 PostgreSQL 설정하기 - Claude](https://claude.ai/chat/3517eb86-807d-42e0-b77e-35b8a7ab7dbd)

Prod
Postgres


빌드는 대체 뭘 하는 건지 아직도 감이 안온다.

마이그레이션과 빌드 분리

prisma migrate deploy를 빌드 단계에서 빼고,
Start Command로 옮기면 된다.
```json
{
  "scripts": {
    "build": "prisma generate && nest build",
    "start:prod": "prisma migrate deploy && node dist/main"
  }
}
```

node dist/main은 뭐꼬

Move database migrations out of the build script and into a preDeployCommand. The build fails because the npm build script runs "prisma migrate deploy", which tries to connect to the database during the build stage where Railway's private network is not accessible. The error "P1001: Can't reach database server at postgres.railway.internal:5432" confirms this.

여기서 두 가지 중 하나일 거예요: 둘다 아니고 Railpacks인데
- **Builder: Nixpacks** (기본값, Dockerfile이 없으면 자동으로 이걸 씀)
- **Builder: Dockerfile** (프로젝트에 `Dockerfile`이 있으면 자동으로 감지됨)

Postgre는 켜져 있는데, 
마이그레이션 전에 Database를 만들어야 하나?
Railway 에서

---
- Repository: `git@github.com:dajhiro/textube-backend.git`
- Git