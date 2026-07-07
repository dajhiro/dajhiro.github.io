# GUI, Graphical User Interface
vs CLI, Command-line Interface


### 창(멀티태스킹) vs 단일


### 브라우저: [브라우저 인터페이스 숨김 모드로 웹앱 경험 개선 - Claude](https://claude.ai/chat/ff392248-c9a6-4c55-8078-826fc989f33f)
웹앱의 불편함을 극복할 방법이, 반드시 브라우저의 키들, 버튼들 등 때문에 브라우저 자체를 포기하는 것이 아니다. 브라우저에서 이용되는 인터페이스들을 모두 없애는 모드를 만들면 된다. 예를 들어서 전체화면 모드가 있다.

PWA(Progressive Web App)의 display mode
```json
// manifest.json
display: {
  "fullscreen", // 화면 전체 차지, 시스템 UI(상태바 등)까지 숨김
  "standalone", // 주소창, 탭바, 네비게이션 버튼 등 브라우저 UI를 숨기고 마치 네이티브 앱처럼 보이게 함
  "minimal-ui", // 최소한의 네비게이션 컨트롤만 남김
  "browser" // 일반 브라우저 탭처럼 UI를 그대로
}
```



---
- 비트맵

브라우저 