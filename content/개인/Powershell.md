설치한 패키지: `winget`
기본:
- [x] `vim`
- [x] `git`

[[../개인/Java]]를 Powershell에서 사용:
- JDK, Java Development Kit
- IntelliJIDEA
- Gradle(Build Tool)
- DBeaver(DB Tool)

Node

---
### 소프트링크 Symbolic link
```powershell
New-Item -ItemType SymbolicLink \
  -Path "from" \
  -Value "target"
```

## 설정
```powershell
vim $PROFILE # 편집
. $PROFILE   # 적용
```

### Alias
```powershell
Set-Alias vi vim
Set-Alias open Start-Process
```

Emacs Keybound
```powershell
Set-PSReadLineOption -EditMode Emacs
```


