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
New-Item -ItemType SymbolicLink -Path "<from>" -Value "<target>"
```

### 설정
### Alias

```powershell
vim $PROFILE
. $PROFILE
```

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

```powershell
Set-PSReadLineOption -EditMode Emacs
```


