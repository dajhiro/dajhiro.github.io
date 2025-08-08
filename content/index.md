## [[프로젝트]]
- [[Metroidvania project]]
- [나의 Unity 문서](Unity)

## [[도구]]
- [[PowerShell]]
- [[Quartz]]
- [[Notion]]
- [[Vim]]
- 색상

- [x] (완료)집주인님 와이파이 빌려야겠음
### Quartz
반영이 너무 느리고 번거롭다. 특히 설정값이.
자동으로 반영만 된다면 훨씬 좋을텐데...
윈도우에는 [[스케줄러]]가 없나?

## Quartz 자동화: 윈도우 작업 스케줄러: `AutoSync.bat`
### `.bat` 파일 생성
```powershell
# AutoSync.bat
@echo off
cd "C:\Users\kuzed\quartz"
npx quartz sync
# pause
```

### 윈도우 작업스케줄러 추가
순서: **작업 스케줄러** → **작업 만들기**
- **일반**
	- **이름**: Quartz Sync Automation
	- **사용자 로그온 여부와 관계없이 실행**: 백그라운드 설정
- **트리거**: 새로 만들기
	- **작업 반복 간격**: 10분
- **동작**: 새로 만들기
	- **프로그램/스크립트**: `C:\Users\kuzed\AutoSync.bat`

### 현재 작업 스케줄러 확인하기
![[Pasted image 20250808134034.png|500]]
- 왼쪽 사이드바에 **작업 스케줄러 라이브러리**를 클릭하면 현재 스케줄러들이 나옴


---
## 기타
- [[Welcome|Private]]
	- [[AutoHotKey]]