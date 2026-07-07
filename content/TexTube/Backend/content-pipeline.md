## Memo
### Todo: 우선순위 순
- [ ] 세션을 받을 수 있도록
- [ ] 처리 종료 후 알림을 받을 수 있도록
- [ ] Redis Queue 도입

Pipeline 생성하는 단계
Persistence 데이터를 저장하는 단계

ContentGenerator
ContentPipeline

GeneratedPostDataDto는 표준 규격



### 질문
웹 페이지에서 업로드 버튼을 눌렀을 때 들여보내는 컨트롤러는 어떻게 어디에 구현하는게 좋을까? 저기에 바로 들어가게 해?

### 로그는

   
### 프론트엔드 고려

## 구조
### service 의존성
- `createPostFromUrl()`
    - `generatePostData()`
        - `extractVideoId()` => utils로 분리
        - `innertubeService`
        - `youtubeDataService`
        - `prisma`
        - `postsService`

youtube.utils.ts

prisma.upsert가 뭔데













