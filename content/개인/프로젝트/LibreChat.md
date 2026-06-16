

**아키텍처 복잡도**
- 모노레포 구조 (client / api / packages 분리)
- React + Express + MongoDB + Redis 스택이 유기적으로 얽혀 있음
- WebSocket 기반 스트리밍 처리가 핵심인데, 이걸 제대로 구현하려면 손이 많이 감

**AI 연동 레이어**
- OpenAI, Anthropic, Google, Azure, Ollama 등 다수 프로바이더를 추상화해서 통합하는 구조
- 각 프로바이더마다 다른 스트리밍 포맷, 토큰 계산 방식, 에러 핸들링을 일관되게 처리해야 함
- 이 부분이 사실상 LibreChat의 핵심 노하우

**상태 관리 & UX**
- 대화 히스토리, 파일 업로드, 멀티모달, 프리셋 관리 등 상태가 복잡함
- 클라이언트 쪽 Recoil + React Query 조합도 꽤 정교하게 설계되어 있음

**인프라**
- Docker Compose로 여러 서비스 오케스트레이션
- 인증 (로컬 + OAuth), 권한 관리, rate limiting 등도 다 직접 구현되어 있음

---
### [[배포 방식]]
솔직히 이 방식은, 개발자가 아니면 전혀 손댈 수 없어.
**셀프 호스팅 (Self-hosted)**
- 사용자가 직접 서버에 올려서 운영
- LibreChat, Ollama, n8n, Supabase 등이 대표적
- Docker Compose가 사실상 표준 배포 방법

**관련 용어들**
- **On-premise** → 기업이 자체 인프라에 올리는 경우 (더 격식체)
- **Self-deployable** → 배포 가능한 오픈소스라는 의미 강조
- **Headless** → GUI 없이 CLI/API로만 운영 (조금 다른 맥락)
- **Server-side app** → Desktop app 없이 서버 필요한 앱