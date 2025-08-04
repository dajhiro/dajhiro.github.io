```Powershell
chokidar "content/**/*.md" -c "npx quartz sync" 
```

`*.md` 파일을 감지하지 못하는 이유가 도대체 무엇일까?
빡대가리라서?