[[Prisma 학습]]


직접 테스트하기

시드 넣기

프로덕션 환경에서는
package.json에서 
```

```

이건 왜 하는거야? 클라이언트 최신화
```
npx prisma generate
```

데이터 리셋
```
npx prisma migrate reset
```

### 마이그레이션: 다음 두 단계로 진행
Schema
```
// prisma/schema.prisma
model User {
  id    String @id @default(uuid())
  email String @unique
  posts Post[]
}
```

Migrate
```
npx prisma migrate dev --name add_posts
```

### 사용하기

