## [[Astro]]: AI 도구 사용하기
### 컨텍스트 파일
`llms.txt` 및 `llms-full` 파일을 AI 소비에 최적화된 형식으로 제공
[[MCP 서버]]는 실시간 검색 기능을 통해 전체 문서에 보다 효율적으로 액세스 가능

### Astro Docs MCP *Model Context Protocol* 서버
이를 통해 AI 도구에 최신 Astro 지식이 있는지 확인할 수 있음
최신 문서에 실시간으로 액세스 가능
Astro Docs MCP 서버는 kapa.ai API를 사용하여 최신 색인을 관리

서버 상세 정보
- 이름: Astro Docs
- URL: `https://mcp.docs.astro.build/mcp`
- 전송 방식: 스트리밍 가능한 HTTP

### 설치
AI 개발 도구에 따라 다르다
일부 도구는 MCP 서버를 커넥터, 어댑터, 확장 또는 플러그인으로 참조

### 직접 설정
많은 도구가 JSON 구성 형식을 지원
`mcp.json`
```json
{
  "mcpServers": {
    "Astro docs": {
      "type": "http",
      "url": "https://mcp.docs.astro.build/mcp"
    }
  }
}
```

### Claude Code CLI
Claude Code는 명령줄에서 실행되는 에이전트 코딩 도구
Astro Docs MCP 서버를 활성화하면
Astro 코드를 생성하는 동안 최신 문서에 액세스 가능

```sh
claude mcp add --transport http astro-docs https://mcp.docs.astro.build/mcp
```

### Claude Code GitHub Action
Claude Code는
- GitHub 이벤트에 대한 응답으로 명령을 실행하는 데 사용할 수 있는
- GitHub 액션도 제공합니다.

Astro Docs MCP 서버를 활성화하면
- 댓글로 질문에 답변하거나
- Astro 코드를 생성하면서 최신 문서에 액세스할 수 있다

워크플로 파일에 다음을 추가하여 Astro Docs MCP 서버를 사용하도록 구성
```yml
- uses: anthropics/claude-code-action@beta
  with:
    anthropic_api_key: ${{ secrets.ANTHROPIC_API_KEY }}
    mcp_config: |
      {
        "mcpServers": {
          "astro-docs": {
            "type": "http",
            "url": "https://mcp.docs.astro.build/mcp"
          }
        }
      }
      allowed_tools: "mcp__astro-docs__search_astro_docs"
```

### 사용하기
AI 도구에 Astro에 대해 질문할 수 있음
