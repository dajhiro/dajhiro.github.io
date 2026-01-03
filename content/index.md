- [[Private]]
- [[Projects]]
- [[이력서]]

### [[TexTube/TexTube]] 출시까지 남은 기간
- [x] 251231(수)
- [x] 251230(화)
- [x] 251229(월)
- [[버그]]
- TexTube 프론트엔드: [[Next.js]]
- TexTube 백엔드: [[NestJS]]

## 260102(금)
TexTube는 youtube 영상을 글로 옮기는 서비스야
Post에서 id는 일단 youtube 상 게시글 id로 할 거라서 int는 안돼
추후 youtube 말고 다른 페이지에서도 글을 옮길 거라서 출처를 남기기는 해야해
그리고 반드시 원작자의 프로필: 이름, 사진
을 넣어야 하거든 그게 author야

글을 공유한(옮긴) 사람의 id (Textube 내의 유저)는 별도로 보관할거야

Youtube에서 해당 게시자가 회원탈퇴하면 영상은 어떻게 되나?

게시글
좋아요 누른 사람들의 목록
TexTube에서 게시글은 공공 소유야 근데
삭제하고 싶은 것들은 처음 사람이 지울 수 있게 할 건데
그 사람이 회원탈퇴하면 삭제할 수 있는 사람이 없어져버려

그냥 익명화로 바꿔버릴까? 그럼 트롤들이 많아질 거 같기도 하고


삭제 권한을 아예 없애버리면 

비공개 게시글을 만들긴 할거고

좋아요라는 기능으로 모든 사람들의 
타임스탬프는 좀 

내 포스트

아 몰라 일단 나 혼자 사용할 수 있게 해야겠다.
그 다음에 생각할래
내가 만든 것들은 내가 지우면 되잖아?

Youtube API key
https://www.googleapis.com/youtube/v3/videos?part=snippet&id=Cm8DPglzEgE&key=

정보는 다음과 같이
이제 캡션을 가져오려면

youtube-transcript

Postman
zsh에서 환경변수 저장하기

비공식 방법이란 걸 몰랐네

```json
"captions": {
  "playerCaptionsTracklistRender": {
    "captionTracks": [
      {
        "baseUrl": "https://*.com/...",
        "name": {
          "simpleText": "English"
        },
        "vssId": ".en",
        "isTranslatable": "true",
        "trackName": ""
      },
      {
        "...": "..."
      }
    ]
  }
}
```
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

[[Schema]] Schema 작성하기

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
[[Claude Code]]

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















