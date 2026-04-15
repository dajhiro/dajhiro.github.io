- [[백엔드 보안]] 
- [[TexTube 개발]]

TexTube는 YouTube 영상을 글로 옮기는 서비스야
- [[개발 기록]]

참조
- [Eightify](https://eightify.app)

## Todo: Features
추가기능: 우선순위 순서로
- [ ] [[Publish/TexTube/언어 기능]] 기능: 메뉴에 추가
- [ ] 스킨 기능: 메뉴에 추가

## Todo: MVP
[[Backend/백엔드]]
- [ ] `/posts` 에서 필요한 값만 출력하도록 엔드포인트 수정
- [ ] Category를 직접 지정할지? 또는 임의로 생성하게 할지?
- [ ] `isReady`가 작성 중일때는 `false`로, AI 응답이 끝났을 때에는 `true`

프론트엔드
- [ ] 모달창좀 어떻게 해봐

업로드 시도 => 

- 세명이 한꺼번에 넣음
    - 이미 존재함

## 클로드 한도로 찔끔 수정
프론트엔드
- [ ] 찔끔합시다

### 프론트엔드
Next Image 모듈 폐기: 게시글 상세
`<Image />` 버리기
`<img />`로 치환

게시글 목록: PostCard
사진을 16:9로 조정

Medium에서는 위쪽에만 마진이 존재한다.
Newneek에서는 위쪽의 마진이 더 넓고 아래쪽도 존재한다.
Reader Mode에서는 위아래의 마진이 동일하다.

### AI 문제들
https://gemini.google.com/app
글 끊김
```ts
config: {
  maxOutputTokens: 4096, // 넉넉하게
  temperature: 0.7,
}
```

프롬프트 수정
```
##, ###까지만 (#는 제목이므로)

```


에러처리
- 자막이 존재하지 않습니다
- AI 가 

## 260107(수)
### Commit
- [x] `extractVideoId()` => `common/utils/youtube.js` 생성 후 옮김

https://ui.shadcn.com/docs/components

### 한도가 걸려서 건드리지 못할 때
지금 커밋하려는 상황에서 Limit이 걸려서 건드리지를 못하겠어. 얘가 컨텍스트를 유지해서 자기가 수정한 내용만 알아서 커밋을 잘 할 수 있을까?
흠 무섭군 무서워...

shadcn/ui 도입
- 이거 자동화하는 게 존재하나보네
- Vercel v0.app

백엔드 배포 성공

Claude Code를 다시 사용하려면 1월 8일 5시까지 기다려야 해요
내가 쓴 일주일치 용량만 Extra로 사용하면 요금이 얼마나 나갈까?
이제 비용 효율화를 신경써야할 때가 왔다

`/compact`

업로드 만들어야 하고... 해야하는데 
일단 isReady가 곧바로 안됨
테스트를 너무 Claude Code에 의존함
커밋 메시지를 Claude Code에 의존함
DB 확인 등을 모두 Claude Code에 의존함

커밋 메시지를 입력하게 해야해서 컨텍스트를 보존시켜야 하는데

업로드 엔드포인트를 어떻게? 현재 feature 안에 있는데 
domain 영역에 새로 만들어야 하나.

### 데이터 수신
JSON 데이터를 백엔드 엔드포인트에서 조절할까
아니면 프론트엔드에서 잘라서 사용할까?
백엔드에서 자르자.
List를 출력할 때랑
Detail을 출력할 때랑 전달하는 값을 다르게 하자.

근데 검색 기능은 또 어떻게 해야할까?

### Pro를 사용할까 Max를 사용해야할까?
Max: 해봤자 한도는 5배밖에 안함
그러니 비용 효율화를 꾀하는 수 밖에

### Todo
프론트엔드
- [ ] 유튜브 사진을 16:9 사이즈로: 현재는 1:1
- [ ] ui.shadcn에서 불러온 것들:
    - [ ] 메뉴가 투명하다? 왜지
    - [ ] 버튼

백엔드
- [ ] 일단 isReady가 곧바로 안됨
- [ ] 테스트를 너무 Claude Code에 의존함
- [ ] 커밋 메시지를 Claude Code에 의존함
- [ ] DB 확인 등을 모두 Claude Code에 의존함

## 260106(화)
[[Frontend]]

와 한번에 너무많이 하니까 머리가 터질 것 같다
여기까지가 내 실력인가 보다
핵심개념 Railway 환경변수

- 구조 정리하기
- package.json 필요없는 거 정리하기
- !실패: youtube.js(InnerTube)로 바꾸기
    - InnerTube 분기화 legacy/new
- 스키마 [[Prisma]]
    - Channel 마이그레이션이 안된 거 구현
    - 최종 스키마를 확정해야함
        - Comment나 또다른 기능은 추후에 확장하기만 하면 되는데,
        - Post, User 등은 새롭게 추가할 것이 아니라면 이제 최종 결정을 해야함.
    - 직접 Dump하고 prisma를
- [[배포]]: Railway

아니 claude code가 구버전으로 착각하고 schema.prisma에다가 env를 넣는 거 같다.
이 프리즈마가 내 시간의 50%를 잡아먹는 거 같다.


## 질문
- [i] Health Check
- [x] `railway.toml` 필수?
- [ ] prisma studio가 무엇인가
    - https://gemini.google.com/app/99a1c4bbf5d08575
- [ ] 테스트 엔드포인트: 어떤 방식으로 테스트하는 게 좋은가?
- [ ] 인가
- [ ] 프로덕션 엔드포인트: 
- [ ] 게시글 목록
- [ ] 게시글 상세

### 게시글 상세


### [[게시글 목록]]
아! 서비스는 서비스대로
HTTP를 받는 건 **컨트롤러** 밖에 없구나

페이지네이션
무한 스크롤: 커서 사용

기본: 최신순, 

정렬 순서
- 최신순
- 인기순
- 알고리즘

카테고리: 전체
태그: 
최신순
인기순


### 프로덕션 엔드포인트
세션 쿠키가 들어온다.
인증: Guard
인가: req.user
데이터 바인딩
### 인가... 
일단 필요한 기능: 회원 탈퇴
DELETE로 보내는 게 일반적인 CRUD 관점에서는 좋다는데
정책이 있다고?? 아 나중에 생각해

### 테스트 엔드포인트
NestJS app.controller에다가
테스트 엔드포인트를 다 때려박은 거 같은데 이따가 지워야 하나?
그럼 어떤 방식...
test/app.e2e-spec.ts로 옮기란다.
- 테스트는 기본적으로: 엔드포인트 테스트와 단위 테스트로 나뉜다.

### railway.toml
이게 없으면: 
- 언어 감지: `package.json`을 보고 Node.js 환경을 탐지
- 빌드 명령어 추측: `build` 스크립트를 찾아서 실행
- 실행 명령어 추측: `start` 스크립트를 찾아서 실행

### Schema
얘네는 왜 두개씩 만들어야하지?
```prisma
  channelId    String
  channel      Channel    @relation(fields: [channelId], references: [id])

  userId       Int
  user         User       @relation(fields: [userId], references: [id])
```

Channel은 Prisma에서 사용하는 거다.

### AI 용량이 모두 고갈될 때


### 각 에러처리를...
어떤 부분에서 하면 좋을까?

### 프로젝트를 여러개 만들면 gemini-flash의 무료 한도를 계속 쓸 수 있나?
https://gemini.google.com/app/65846c57efeaf6ae
=> 가능: 와 프로젝트당 키를 3개까지 만들어서 한도를 조금만 늘려보자

### NestJS 모듈 컨벤션
모듈이 커질때에는 users, posts, channels 등...을 또 다른 폴더를 만들어서 분류해야 할까?


```
  src/
  ├── core/                   # Framework & database setup
  │   ├── prisma/             ✓ (prisma module, service, tests)
  │   └── auth/               ✓ (auth module, service, controller, strategies, guards)
  │
  ├── integrations/           # External APIs (Low-level)
  │   ├── ai/                 ✓ (Gemini AI service, prompts, DTOs)
  │   ├── youtube-data/       ✓ (YouTube Data API v3)
  │   └── innertube/          ✓ (YouTube transcript extraction)
  │
  ├── features/               # Business logic (High-level)
  │   └── content-pipeline/   ✓ (Orchestrates all integrations)
  │
  ├── domain/                 # Data & CRUD
  │   ├── users/              ✓ (User module, service, controller, DTOs)
  │   └── posts/              ✓ (Post module, service, controller, DTOs)
  │
  └── common/                 # Shared utilities
      └── types/              ✓ (Express type definitions)
```

tsconfig.json
```
"paths": {
  "@modules/*": ["src/modules/*"],
  "@integrations/*": ["src/integrations/*"],
  "@core/*": ["src/core/*"]
}
```

**모듈 경계 준수:** `integrations`에 있는 모듈(예: `ai`)은 가급적 우리 서비스의 DB 엔티티를 직접 알지 못하게 하고, `dto`나 `interface`로만 소통하는 것이 좋습니다.

### 에러 처리에 관한 고민
각 모듈화 분리에 성공하면 에러 처리도 수월해질 거 같은데
조금 무섭다.

## TODO
### 백엔드
- [x] Channel 테이블 만들기
- [ ] Post 기능: find 후
    - 있으면 등록
    - 없으면 새로 생성 후 등록
- [x] 포스팅 테스트하기
- [ ] User에 capacity 컬럼 만들기
    - [ ] capacity를 태평양 시각 자정을 기준으로

### 파이프라인
- [ ] 해당 id가 있는지 먼저 검사하기

### 프론트엔드
- [ ] 폼 모달창 만들기
    - 구조
        - URL 넣는 공간
        - 공개 체크박스(기본값)
        - 내 유저정보 (Hidden)
        - 보내기, 취소(또는 모달창 밖에 누르면 사라짐)
    - 업로드 버튼을 눌렀을 때
        - 로그아웃 상태 => 로그인 모달
        - else => 업로드 버튼 

[[프론트엔드]]
테스트를 어떻게 하지?
title은 유튜브 제목 그대로 하고 싶은데 일단 AI로 하자.

front
PENDING 상태일 경우 비활성화 사진이랑 

[[Post]]
각 API가 무슨 역할을 맡는지
- youtubeId
Youtube Data API
- thumbnailUrl
- channel
    - id
    - name
    - image
AI
- category
- tags
- metadata
    - seo
    - ai_stats
InnerTube API
- Caption


핵심기능

PostsService

프롬프트 외부화
Constants 파일

모듈 네이밍 컨벤션
- [x] 기술 스택(API) 중심
- [ ] 기능 중심
  
### 인증
Next 인증 상태 Context 설정하기

### [[Post]]
category 추가

markdown frontmatter

### SSR 전략
AI를 사용했을 때
마크다운으로 출력받기
json으로 출력받기

### 다음 프롬프트
```
스키마를 확인해서 새롭게 추가된 것들을 적용하기 위해 Youtube Data API V3가 필요해
Youtube Data API
```

Youtube Data API: 유튜브 영상 id로
channel 정보 DB
- Channel id
- Channel name
- Channel profile photo url
- Channel Link: id로 url을 만드므로 따로 없어도 됨

thumbnail url 추출

`viedos.list`
- `channelId`
    - db에 존재하지 않으면 새로 생성 후
        - `channel.list`로 name, image 추출
- `thumbnails`
    - 가장 큰 사이즈의 url

metadata 
```json
{
  "seo": {
    "title": "AI가 생성한 최적화 제목",
    "description": "이 글의 핵심 내용을 150자 내외로 요약한 문장",
    "ogImage": "https://cdn.example.com/generated-cover.png",
    "keywords": ["AI", "SSR", "PostgreSQL"]
  },
  "content_info": {
    "reading_time": 5,
    "word_count": 1240,
    "difficulty": "Intermediate",
    ]
  },
  "ai_stats": {
    "model": "gemini-1.5-pro",
    "version": "2.0",
    "generated_at": "2026-01-05T15:00:00Z",
    "prompt_tokens": 450,
    "completion_tokens": 1200
  },
  "youtube": {
  }
}
```

세 모듈을 추가할거야
- AI API 모듈
- Youtube Data API 
- InnerTube API

PostgreSQL Prisma

id


Essential
- title
- description
- publishedAt
- creator

Organization
- category
- tags
- status

Visuals
- thumbnailUrl
- ogImage

Core
- content
- toc


### o
TexTube는 YouTube 영상을 글로 옮기는 서비스야
[[TexTube/textube_strategy_analysis]]

[[Next.js NestJS 연결]]

InnerTube API로 할 수 있는 것
일단 유튜브 URL에서 뽑아내야 하는 것
- Youtube URL
- 썸네일 URL

다음에 해야하는 것


Backend 마저
[[Textube/Backend/Schema|Schema]]
[[Get Transcript]]
[[TexTube/YouTube Data API]]

Post에서 id는 일단 유튜브 상 게시글 id로 할 거라서 int는 안돼 => string
추후 youtube 말고 다른 페이지에서도 글을 옮길 거라서 **출처**를 남기기는 해야해
그리고 반드시 원작자의 프로필: 이름, 사진
을 넣어야 하거든 그게 author야

글을 공유한(옮긴) 사람의 id (Textube 내의 유저)는 별도로 보관할거야

Youtube에서 해당 게시자가 회원탈퇴하면 영상은 어떻게 되나?
=> 삭제된다
TexTube에서는? 
=> 그대로 둔다

### 게시글
좋아요 누른 사람들의 목록
TexTube에서 게시글은 공공 소유야 근데
삭제하고 싶은 것들은 처음 사람이 지울 수 있게 할 건데
그 사람이 회원탈퇴하면 삭제할 수 있는 사람이 없어져버려

그냥 익명화로 바꿔버릴까? 그럼 트롤들이 많아질 거 같기도 하고
삭제 권한을 아예 없애버리면 

비공개 게시글을 만들긴 할거고

좋아요라는 기능으로 최초 제공자, 이용자를 포함
타임스탬프는 좀 

내 포스트
아 몰라 일단 나 혼자 사용할 수 있게 해야겠다.
그 다음에 생각할래
내가 만든 것들은 내가 지우면 되잖아?

정보는 다음과 같이
이제 캡션을 가져오려면

youtube-transcript

Postman
zsh에서 환경변수 저장하기

비공식 방법이란 걸 몰랐네

[[TexTube/Youtube Transcript API]]
`data.captions.playerCaptionsTracklistRenderer.captionTracks`

asr은 하나밖에 없으니까 
asr로 언어를 탐지하고
자막이 존재하면

`t.kind === 'asr'` 의 
`languageCode`를 확인해서
`!t.kind`인 목록들 중에서
`languageCode`에 해당하는 자막을 선택
없으면 그냥 `t.kind === 'asr'`로 진행

영어랑 한국어가 섞여있는 영상에서는 모두 생략되어 버리네

최적화는 다음에 생각하고 일단 **영상의 언어**로 하자
자막
- 자동 생성
- 캡션 존재

## 251231(수)
### 할일
- [ ] Groq API 사용해보기
- [ ] Youtube API 사용해서 파일 분리하기
- [ ] Gemini API 사용해보기
- [ ] NestJS 구축하기

[[NestJS]]

[[Textube/Backend/Schema]] Schema 작성하기

## 251230(화)
대충 Prisma 사용법은 알겠다.

`@Global`은 뭘까?

### spec
`user.service.spec.ts`는 어떻게 사용하는 걸까?
```ts
import { Test, TestingModule } from '@nestjs/testing';
import { UserService } from './user.service';

describe('UserService', () => {
  let service: UserService;

  beforeEach(async () => {
    const module: TestingModule = await Test.createTestingModule({
      providers: [UserService],
    }).compile();

    service = module.get<UserService>(UserService);
  });

  it('should be defined', () => {
    expect(service).toBeDefined();
  });
});
```

### DB 스키마 설정하기
PostgreSQL를 사용하면 직접 SQL을 넣는 거랑 다른 모듈을 이용하는 거랑 뭐가 좋을까?
TypeORM, Prisma
⇒ Prisma 채택

코딩과 자료 수집 분리 도서관에서 글쓰기와 책 읽기를 분리하듯이
코딩은 hiro 계정에서만
https://console.cloud.google.com/

MCP 서버 이용하는 법

### AI 도우미 
[[../Claude Code/Claude Code]]

### Railway
Railway로 한번 백엔드를 구축해보자. NestJS를 사용한다.
도커로 배포해야 하는건가? 깃허브에는 어떤 파일들을 두어야 하는가?

나는 도커를 사용할 줄 모른다
내가 배포하려는 백엔드, DB 서버를 도커로 옮기려면 어떻게 해야하는가?

### 원래 DB를 백엔드에 포함시키려 했는데
Railway에 Postgre가 존재한다고?

⇒ Railway PostgreSQL 채택

### 백엔드 배포는 어떻게? 
Railway
Cloudflare Workers

⇒ 더 일반적인 Railway로 채택

- [x] 프로젝트에 필요한 [[허용된 웹 사이트 목록]] 추가

## 251225(목)
### 체크리스트
- [x] `10:23` Astro

Astro 폐기
[[Next.js/Next.js]]

[[JavaScript]]

## 251222(월)
체크리스트
- [x] `08:21` 와우...
- [x] `06:58`

- [[Netlify]]
- [[Astro 튜토리얼]]

## 251221(일)
- [x] `15:19`, [[Safari]] 단축키 정리
- [x] `12:04`, 집에 도착
- [x] `10:51`, 두개 독스
- [x] `09:01`, 시작

### [[Astro]] Philosophy
If you need a website that loads fast and has great SEO,
then Astro is for you.

integrations
API hooks

- 콘텐츠 중심
- 서버 우선: MPA *Multi Page Application*
    - <-> Next.js, SvelteKit, Nuxt, Remix 등 다른 JavaScript 웹 프레임워크
    - **필요할 때만** 클라이언트 실행 UI 프레임워크 컴포넌트 추가
    - TTI 
- 기본적으로 빠름
- 사용하기 쉬움

### React
Hooks

Netlify
## [[Astro]] 튜토리얼 ㄱㄱ

페이지

[[Astro]]
- Astro 구성 -- AI 도구
- Astro 구성 -- 환경변수 사용
- [[Astro 구성 -- TypeScript]]
- [Astro 구성 -- 개발자 도구 모음](https://docs.astro.build/ko/guides/dev-toolbar/)


### 기타
- [ ] `<pre>`
- [ ] www.typescriptlang.org
- [ ] [Astro의 재평가](https://claude.ai/chat/2d99b908-5292-4b61-8b81-b7e2bf6c6139)
- [ ] [옵시디언에서 `.astro` 코드블럭 사용하는 방법](https://claude.ai/chat/20dc4031-9557-4e8b-bdae-1f024d84282c)
### 새로운 시작
이번주부터는 TexTube 본격적 개발

## TexTube
- [[Frontend]]: [[Next.js]]
    - 배포: [[Cloudflare]] Pages
- [[Backend]]: [[NestJS]]
    - 배포: [[Railway]] + PostgreSQL
    - 파이프라인: API
        - [[Groq]], [[Gemini]]
        - [[Youtube API]]

[[Frontend]]
[[Backend]]
[[Post]]

[[Commit]]

PostgreSQL를 사용하면 직접 SQL을 넣는 거랑 다른 모듈을 이용하는 거랑 뭐가 좋을까?

NestJS 도커파일만 넣으면 된다.
Railway 사용법
Railway DB 사용하는 법

[[TexTube 인증]]

제발

- [[Claude Code]]













