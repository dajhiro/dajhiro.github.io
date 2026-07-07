- [ ] [[#Railway용으로 `main.ts` 수정|main.ts 세팅]]
- [ ] [[#헬스체크 엔드포인트 추가|Healthcheck setting]]
- [ ] 

### Railway용으로 `main.ts` 수정

다음 필수사항 두가지
- 환경변수 PORT 사용: `process.env.PORT`
- 0.0.0.0 바인딩: `app.listen(port, '0.0.0.0');`

```ts
// main.ts
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  const port = process.env.PORT || 3000;
  await app.listen(port, '0.0.0.0');
}
bootstrap();
```


### 헬스체크 엔드포인트 추가
```sh
nest generate controller health
```

```ts
// src/health/health.controller.ts
import { Controller, Get } from '@nestjs/common';

@Controller('health')
export class HealthController {
  @Get()
  check() {
    return { status: 'ok' };
  }
}
```

`railway.json` 설정
(기본값은 대시보드에서 설정)
- Project → Service
	- Settings → Build
		- Builder `Nixpacks` ⇒ `Railpack`

```json
{
  "$schema": "https://railway.app/railway.schema.json",
  "build": {
    "builder": "RAILPACK"
  },
  "deploy": {
    "startCommand": "npm run start:prod",
    "healthcheckPath": "/health",
    "healthcheckTimeout": 100,
    "restartPolicyType": "ON_FAILURE",
    "restartPolicyMaxRetries": 10
  }
}
```

커스텀 빌드 설정: `railpack.json`
```json
{
  "$schema": "https://railway.app/railway.schema.json",
  "provider": "node",
  "steps": {
    "install": {
	  "commands": ["npm install"]
    },
    "build" {
	  "commands": ["npm run build"]
	}
  }
}
```

### 공공 도메인 만들기
my-railway-app → Settings → Networking → Public Networking
**Generate Domain**














