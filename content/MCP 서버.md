https://claude.ai/chat/25a7fb2f-e316-4d3a-b56d-d1b96ade885a
### Model Context Protocol (MCP) Server
Anthropic이 개발한 개방형 프로토콜
AI 애플리케이션이
외부 데이터 소스나 도구들과
안전하고 표준화된 방식으로 연결

통신 방식: JSON-RPC 2.0 기반의 메시지 교환
목적: AI <-> 다양한 외부 시스템

### 역할
- 특정 데이터 소스(예: DB, File System, API)에 대한 접근 제공
- 특정 도구나 기능(예: 검색, 계산, 코드 실행)을 AI가 사용할 수 있게 노출
- 보안과 권한 관리를 표준화된 방식으로 처리

### 실제 예시
- Google Drive MCP 서버: Claude가 여러분의 Google Drive 파일에 접근
- Slack MCP 서버: Claude가 Slack 메시지를 읽고 쓸 수 있음
- GitHub MCP 서버: 코드 저장소 관리
- 데이터베이스 MCP 서버: SQL 쿼리 실행

```json
{
  "jsonrpc": "2.0",
  "method": "tools/call",
  "params": {
    "name": "search_files",
    "arguments": {
      "query": "2024년 보고서"
    }
  },
  "id": 1
}
```

















