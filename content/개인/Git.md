# Git
- [[Git/커밋 탐색]]
커밋 두개 합치기
```git
git rebase -i --root
```


[Git 커밋으로 프로젝트 변화 추적하기 - Claude](https://claude.ai/chat/0d7ab554-1679-4386-b123-c037f4617479)
### 언제 커밋을 해야하는가?
논리적으로 완결된 작업 단위 마다

1. 하나의 기능/버그 수정이 완료되었을 때
2. 코드가 정상적으로 동작하는 상태 — 빌드가 되고, 테스트가 통과하는 시점
3. 리팩토링 전/후
4. WIP(work in progress) 커밋으로 넘기고, 나중에 `rebase -i`로 정리하기

### Git으로 개발 배우기
Git으로 만들어진 프로젝트
Init부터 커밋을 따라서 코딩을 배워보기.
목표는 이 앱이 어떻게 만들어진 것인지 보는 것
커밋 관리 GUI가 필요할까?
`git`만으로는 부족할까?


[[Git — 도구]]

### CLI
```
git log --oneline --graph --all
```

Init부터 보기
```
git log --reverse --oneline
```

각 커밋의 diff 보기
```
git log --reverse -p
```

- patch: `-p`
	- diff 형태로 보여준다.

특정 커밋만 보기
```
git show <commit-hash>
```

그 지점 코드를 체크아웃하여 실행해보기
```
git checkout <commit-hash>
```





[[dotnet]]









