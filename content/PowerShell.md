
## 몰라
심볼릭 링크 지우는 법
Alias 설정

---
연관
- [[Vim]]
## Emacs
새로운 명령어
- `Ctrl-x Ctrl-u`
	- 되돌리기 1회
## 설정
### Windows Terminal
투명도
- 모양 → 투명성 → 배경 불투명도
	- 75%
- 모양 → 투명성 → Blur(아크릴 재질 사용)
커서
- 모양 → 커서 → 커서 모양
스킨
- [[iTerm 컬러셋]]``

## PowerShell
Emacs 모드
```powershell
Set-PSReadLineOption -EditMode Emacs
```

심볼릭 링크 생성하기: 관리자모드 전용
```powershell
New-Item -ItemType SymbolicLink -Target "[Target]" -Path "[Path]" 
```

심볼릭 링크 지우기
```PowerShell
알려줘
```

---
추가
- 개발자 모드로 하는 방법도 있다는데?
