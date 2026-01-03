[[Prisma 학습]]
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

