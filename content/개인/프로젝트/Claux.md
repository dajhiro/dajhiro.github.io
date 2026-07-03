## [[개발 프롬프트]]
### 플랫폼
- Chrome Extension
- 개발불가

기능
- [[질문 접기]]

## Manifest V3 제약 조건
[[확장프로그램]]
### 1. Service Worker
- `chrome.storage`, `IndexedDB` 등의 영속 저장소를 반드시 사용해야 함
- WebSocket 연결, 타이머 유지 등이 까다로워짐

### 2. 네트워크 요청
`declarativeNetRequest`
동적으로 가로채고 수정하는 기능 이제 불가능
정적으로 미리 선언한 규칙만 사용 가능

```json
{
  "id": 1,
  "action": { "type": "block" },
  "condition": { "urlFilter": "ads.example.com" }
}
```

### 3. 원격 코드 실행 불가능
동적 JS코드 금지
반드시 확장 프로그램

### 5. Content Security Policy (CSP)


### 6. Promise 기반 API



---
이름을 무엇으로 할까?

---

Obisdian
- ⇒ Claude
- ⇒ [[Chat]]: Telegram
- ⇒ Web

프라이버시 및 보안

[Safari iOS 하단 주소창 사용성 지표 - Claude](https://claude.ai/chat/9c1a0cb2-9533-44b4-975e-e92981b3915e)
핵심 기능
- 접기 기능
	- 질문-답변 관리
- 채팅 관리

타겟
- 웹 브라우저로 
- 크롬

지향점
- 웹 브라우저 이용을 촉진
	- 사파리, 크롬(엣지)

---
- 플랫폼Platform 별 기능을 극대화하는 방식은 무엇인가?
- 지금 내가 Claude.ai 웹앱에 익숙한 것은,
	- 그 페이지에 대한 관성 때문인가?
	- 브라우저에 대한 관성 때문인가?
	- Safari iOS에서는 사용하기 불편하다. 주소창이 하단에 있기  때문이다.
		- 모바일 브라우저 [[하단 주소창]]
	- iOS에서 좌측 상단 뒤로가기 버튼이나,
		- 좌측 하단 뒤로가기 버튼을 누르는 걸 편하게 여기는 사람이 얼마나 될 것인가?
	- 

국내에서 Safari의 인기가 없는 이유는

나의 목표는 결국 사람들이 Mac에 환장하도록 만드는 것
iPhone에 환장하도록 만드는 것
그리고 그 열광을 내 제품으로 옮기는 것

Smoothly
나는 Continuity를 이야기하는 것