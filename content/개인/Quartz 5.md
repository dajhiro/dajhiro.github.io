# Quartz 5
### Todo
- [ ] 테마를 바꾸고 싶다.
	- [x] Font

### 목차
- [[Quartz 5 — Plugins]]
- [[Quartz 5 — Migrating]]
- [[Quartz 5 — Hosting]]



바꾸고 싶다

어떻게 사용하는데?
%%hidden%%

docker
```sh
docker run --rm -itp 8080:8080 -p 3001:3001 -v ./content:/usr/src/app/content $(docker build -q .)
```

### 셋업
```powershell
# 클론
git clone "https://github.com/dajhiro/dajhiro.github.io"

# 세팅
cd dajhiro.github.io
npm install
npx quartz sync
```

### 심볼릭 링크 연결
```powershell
cmd /c mklink /J "C:\Users\BOC.DESKTOP-GEI5MRB\문서\Obsidian\업무용\개인" "C:\Users\BOC.DESKTOP-GEI5MRB\Projects\dajhiro.github.io\content\개인"
```

