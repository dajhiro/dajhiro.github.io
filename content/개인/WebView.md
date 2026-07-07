### 웹뷰[[WebView]]가 드럽게 느린 이유
[Webview 성능 저하와 HTTP/2.0 지원 - Claude](https://claude.ai/chat/8f83afc0-5e9b-4eda-963d-df08956f98b5)
실제 느린 이유
- WebView 프로세스 초기화/워밍업
	- WebView 인스턴스
- JS 번들 파싱/실행비용
- 네이티브 ←> 웹 브릿지 통신
	- JS Bridge를 통한 메시지 직렬화/역직렬화
		- 특히 postMessage 기반 브릿지
- 캐싱 전략
	- WebView 캐시 정책, 
- API 체이닝 구조

---
[[../개인/Mobile]]
Android WebView
Apple iOS WKWebView

웹뷰의 장점: 배포 없이 업데이트해요
앱을 배포하려면 스토어 심사가 필요해요. 하지만 웹뷰를 사용하면 앱 심사를 하지 않아도 웹사이트 내용을 수정할 수 있어요. 자주 바뀌거나 빠르게 업데이트가 필요한 화면은 웹뷰로 구현하세요.
