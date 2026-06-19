
---

### [[Terminal]]
Ctrl+C와 Ctrl+V는 **Windows 콘솔 호스트(conhost.exe) 자체에 하드코딩된 특수 처리**가 있어요:
- **Ctrl+C**: 콘솔이 이걸 보면 PowerShell 프로세스로 `CTRL_C_EVENT` 시그널을 던집니다. 이건 키 입력이 아니라 "이 프로세스를 중단시켜라"는 **프로세스 제어 신호**입니다. PSReadLine까지 도달하기 전에 콘솔 레이어에서 가로채집니다.
- **Ctrl+V**: 콘솔 호스트가 클립보드 API(`GetClipboardData`)를 직접 호출해서 텍스트를 붙여넣는 **콘솔 차원의 기능**입니다. 이것도 PSReadLine의 키 핸들러 체인에 도달하기 전에 conhost가 처리해버립니다.

## [[Setting]]
- System → Multitasking → 

### eXtension
- [[AutoHotKey]]
- ThreeFingerDragOnWindows
- PowerToys

Windwos