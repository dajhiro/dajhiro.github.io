
커밋
- 정보
- 메시지
- Diff

- 커밋 해시 (Hash)
- 작성자 및 날짜 (Author/Date)
- 커밋 메시지 (Subject & Body)
- 변경된 **파일 목록** (--stat)
- 변경사항 (Diff)

## 데이터 추출하기
### 1. Git 자체 명령어

```sh
git log -n 20 --stat --pretty=format:"---%nCommit: %h%nAuthor: %an%nDate: %ad%nSubject: %s%nBody: %b%nFiles Changed:"
```

### 2. GitHub 이용하기
- [[GitHub Copilot CLI]]
	- 자연어로 명령어를 제안받거나
	- 코드를 리뷰하고
	- 테스트를 생성하는 등 강력한 AI 에이전트 기능

이 프로젝트를 만든 사람의 코딩 실력을 네가 커밋들을 분석해서 유추해줘.

gh와는 다른 건가?

Copilot CLI



### AI 이용
분석 페르소나
