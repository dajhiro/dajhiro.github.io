```prisma
enum PostStatus {
  PENDING
  PUBLISHED
}

model Post {
  id           Int        @id @default(autoincrement())
  title        String
  content      String     @db.Text  youtubeId    String     @unique // 유튜브 영상 고유 ID
  thumbnailUrl String     // 유튜브 썸네일 중 가장 큰 사이즈

  // 핵심 메타데이터 (JSONB)
  metadata     Json       @default("{}") @db.JsonB

  // 분류 및 상태
  category     String?
  tags         String[]
  viewCount    Int        @default(0)
  status       PostStatus @default(PENDING)
  published    Boolean    @default(false)

  createdAt    DateTime   @default(now())
  updatedAt    DateTime   @updatedAt

  // 관계 설정
  channelId    String
  channel      Channel    @relation(fields: [channelId], references: [id])

  userId       Int
  user         User       @relation(fields: [userId], references: [id])

  @@index([youtubeId])
}
```

metadata 예시
```json
{
  "seo": {
    "title": "유튜브 제목보다 더 검색이 잘 되는 AI 최적화 제목",
    "description": "영상의 핵심 내용을 요약한 메타 설명문",
    "keywords": ["리액트", "SSR", "Next.js"]
  },
  "ai_stats": {
    "model": "gemini-2.5-flash",
  }
}
```

나중에 tocs

---
- [[설계]]
