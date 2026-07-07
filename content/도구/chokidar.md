```Powershell
chokidar "content/**/*.md" -c "npx quartz sync" 
```

- [x] `*.md` 파일을 감지하지 못하는 이유가 도대체 무엇일까? 빡대가리라서?
	- `npx quartz sync`에서 파일을 지웠다가 생성해서 그런 듯 하다
	- ⇒ 폐기: [[스케줄러|윈도우 작업 스케줄러]]