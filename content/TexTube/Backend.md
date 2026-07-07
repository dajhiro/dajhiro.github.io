[[../NestJS/NestJS|NestJS]]
### 프로젝트 시작
```sh
nest new textube-backend
```

### 패키지 설치
- ORM: Prisma
```sh
# 인증 관련
npm install @nestjs/passport passport passport-google-oauth20 passport-jwt
npm install @nestjs/jwt
npm install bcrypt

# Prisma
npm install @prisma/client
npm install -D prisma

# 환경 변수
npm install @nestjs/config

# 유효성 검사
npm install class-validator class-transformer

# 타입 정의
npm install --save-dev @types/passport-google-oauth20 @types/passport-jwt @types/bcrypt
```

### [[Prisma]]: User
## Prisma: 로컬 PostgreSQL에 연결하기 
- CLI에서 DB 생성하기
- DB 연결하기
- 스키마 작성하기
- 마이그레이션하기
- 서비스 제공 (접기)

### CLI에서 DB 생성하기
*psql*
```sh
createdb textube
```

### DB 연결하기
*.env*
```env
DATABASE_URL="postgresql://postgres@localhost:5432/test"
```

*prisma.config.ts*
```ts
// prisma.config.ts
export default defineConfig({
  datasource: {
    url: process.env["DATABASE_URL"],
  }
})
```

### 스키마 작성하기
`prisma/schema.prisma` 작성하기

```prisma
datasource db {
  provider = "postgresql"
}

generator client {
  provider = "prisma-client-js"
}

model User {
  id        Int      @id @default(autoincrement())
  email     String   @unique
  name      String?
  posts     Post[]
  createdAt DateTime @default(now())
}
```

### 마이그레이션 하기
```sh
npx prisma migrate dev --name init
```

### 서비스 작성하기
서비스 생성
```sh
nest g module prisma
nest g service prisma
```

*src/prisma/prisma.module.ts*
```ts
import { Global, Module } from '@nestjs/commmon';
import { PrismaService } from './prisma/service';

@Global()
@Module({
  providers: [PrismaService],
  exports: [PrismaService],
})
export class PrismaModule {}
```

*src/prisma/prisma.service.ts*
```ts
import { Injectable, OnModuleInit, OnModuleDestroy } from '@nestjs/common';
import { PrismaClient } from '@prisma/client';

@Injectable()
export class PrismaService extends PrismaClient implements OnModuleInit, OnModuleDestroy {
  async onModuleInit() {
    await this.$connect();
  }
  
  async onModuleDestroy() {
    await this.$disconnect();
  }
}
```

App Module에 등록
*src/app.module.ts*
```ts
import { Module } from '@nestjs/common';
import { PrismaModule } from './prisma/prisma.module';

@Module({
  imports: [PrismaModule],
  // ...
})
export class AppModule {}
```

서비스에서 사용
*src/users/users.service.ts*
```ts
import { Injectable } from '@nestjs/common';
import { PrismaService } from '../prisma/prisma.service';

@Injectable()
export class UsersService {
  constructor(private prisma: PrismaService) {}

  async createUser(email: string, name?: string) {
    return this.prisma.user.create({
      data: {
        email,
        name,
      },
    });
  }

  async findAll() {
    return this.prisma.user.findMany();
  }

  async findOne(id: number) {
    return this.prisma.user.findUnique({
      where: { id },
    });
  }

  async update(id: number, name: string) {
    return this.prisma.user.update({
      where: { id },
      data: { name },
    });
  }

  async remove(id: number) {
    return this.prisma.user.delete({
      where: { id },
    });
  }
}
```

*src/user/user.controller.ts*
```ts
import { Controller, Get, Post, Body, Param, Put, Delete } from '@nestjs/common';
import { UserService } from './user.service';

@Controller('user')
export class UserController {
  constructor(private readonly userService: UserService) {}
  
  @Post()
  create(Body() createUserDto: { email: string; name?: string }) {
    return this.userService.createUser(createUserDto.email, createUserDto.name);
  }
  
  @Get()
  findAll() {
    return this.userService.findAll();
  }
  
  @Get(':id')
  findOne(@Param('id') id: string) {
    return this.userService.findOne(+id);
  }
  
  @Put(':id')
  update(@Param('id') id: string, @Body() updateUserDto: { name: string }) {
    return this.userService.update(+id, updateUserDto.name);
  }
  
  @Delete(':id')
  remove(@Param('id') id: string) {
    return this.userService.remove(+id);
  }
}
```

---
## 질문
- [x] `createUserDto` 직접 만들어야 함
    - [x] 인라인으로 그냥 정의한 것 : `updateUserDto: { name: string }`
- [x] `+id`: id(string)를 숫자로 변환
- [x] **Seeding**: 간단한 Mock 데이터 추가하기

### Prisma Seed: *prisma/seed.ts*
```ts
import { PrismaClient } from '@prisma/client';

const prisma = new PrismaClient();

async function main() {
  await prisma.user.deleteMany();
  
  const user1 = await prisma.user.create({
    data: {
      email: 'alice@example.com',
      name: 'Alice',
    },
  });
  
  const user2 = await prisma.user.create({
    data: {
      email: 'bob@example.com',
      name: 'Bob',
    },
  })
  
  console.log({ user1, user2 });
}

main()
  .catch((e) => {
    console.error(e);
    process.exit(1);
  })
  .finally(async () => {
    await prisma.$disconnect();
  })
```

*package.json*에 등록
```json
{
  "prisma": {
    "seed": "ts-node prisma/seed.ts"
  },
  "scripts": {
    "seed": "npx prisma db seed"
  }
}
```

실행
```sh
npm run seed
```











