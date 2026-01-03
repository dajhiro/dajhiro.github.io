### 1. Prisma Schema
```prisma
// prisma/schema.prisma
model User {
  id    String @id @default(uuid())
  email String @unique
  posts Post[]
}

model Post {
  id       String @id @default(uuid())
  title    String
  authorId String
  author   User   @relation(fields: [authorId], references: [id])
}
```

### 2. Prisma Client
```ts
// 자동 완성, 타입 체크 완벽!
const user = await prisma.user.create({
  data: {
    email: 'test@test.com',
    posts: {
      create: {
        title: 'First Post'
      }
    }
  }
});
```
### 3. Prisma Migrate
```
npx prisma migrate dev --name add_posts
```

---
## 필드/테이블 추가하기
### 1. 스키마 작성
```
// Before
model User {
  id    String @id @default(uuid())
  email String @unique
  name  String?
}

// After - 전화번호, 생일 추가
model User {
  id          String    @id @default(uuid())
  email       String    @unique
  name        String?
  phoneNumber String?   @map("phone_number")  // 새로 추가
  birthday    DateTime?                        // 새로 추가
  createdAt   DateTime  @default(now()) @map("created_at")
}
```

### 2. 마이그레이션 실행
```bash
npx prisma migrate dev --name add_user_fields
```

## 새 테이블 추가
### 스키마 작성
```
// 댓글 기능 추가
model Comment {
  id        String   @id @default(uuid())
  content   String
  userId    String   @map("user_id")
  postId    String   @map("post_id")
  createdAt DateTime @default(now()) @map("created_at")
  updatedAt DateTime @updatedAt @map("updated_at")

  user User @relation(fields: [userId], references: [id], onDelete: Cascade)
  post Post @relation(fields: [postId], references: [id], onDelete: Cascade)

  @@map("comments")
}

// User 모델에 관계 추가
model User {
  // ... 기존 필드들
  comments Comment[]  // 새로 추가
}

// Post 모델에 관계 추가
model Post {
  // ... 기존 필드들
  comments Comment[]  // 새로 추가
}
```











