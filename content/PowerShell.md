
## 몰라
- [x] 심볼릭 링크 지우는 법
	- [x] 그냥 지우면 된다 경고문은 그냥 뜨는 거 ㅆㅂ 안에 파일 다 지워지는 줄 알고 식겁했네
- [ ] 설정: Alias 설정


---
## 설정
### Powershell
Emacs 모드
```powershell
Set-PSReadLineOption -EditMode Emacs
```
### Windows Terminal
투명도
- PowerShell → 모양 → 투명성
커서
- 모양 → 커서 → 커서 모양
스킨
- [[iTerm 컬러셋]]


## 명령어
심볼릭 링크 생성하기: 관리자모드 전용
```powershell
New-Item -ItemType SymbolicLink -Target "[Target]" -Path "[Path]" 
```

심볼릭 링크 지우기
```PowerShell
Remove-Item "[그냥 지워]"
```

## Emacs
새로운 명령어
- `Ctrl-x Ctrl-u`
	- 되돌리기 1회

























