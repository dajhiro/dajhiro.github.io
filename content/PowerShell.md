## 몰라
- [x] `sudo` 비슷하게 하는 법: 없어, [[250809(토)]], 12:13

## 완료
- [x] 이스케이프 문자: 그런거 없다. 그냥 쌍따옴표로, [[250807(목)]], 22:10
- [x] 심볼릭 링크 지우는 법, [[250804(월)]]
	- [x] 그냥 지우면 된다 경고문은 그냥 뜨는 거 ㅆㅂ 안에 파일 다 지워지는 줄 알고 식겁했네
- [x] 설정: Alias 설정, [[250805(화)]]

---
## 설정
### 개인 설정값
설정 파일은 `$PROFILE`에 저장되어 있음.
프로파일 환경변수를 어떻게 설정했는지는 기억이 안남.

```powershell
# $PROFILE
Set-Alias grep Select-String
Set-Alias vi vim # vi가 입력되지 않음
Set-Alias open explorer # Mac Finder
Set-PSReadLineOption -EditMode Emacs # Emacs
```

### Alias
```powershell
Set-Alias [A] [B] # A를 B로 설정한다
```

### 편집
```powershell
vi $PROFILE
```

### 적용
```powershell
. $PROFILE
```

---
## 명령어
### Powershell
심볼릭 링크 생성하기: 관리자모드 전용
```powershell
New-Item -ItemType SymbolicLink -Target "[Target]" -Path "[Path]" 
```

심볼릭 링크 지우기
```PowerShell
Remove-Item "[그냥 지워]"
```

이스케이프 문자? 그런거 없다 그냥 따옴표 들이박어
### Emacs
새로운 명령어
- `Ctrl-x Ctrl-u`
	- 되돌리기 1회

---
## Windows Terminal
투명도
- PowerShell → 모양 → 투명성
커서
- 모양 → 커서 → 커서 모양
스킨
- [[iTerm 컬러셋]]

























