[[ThreeFingerDragOnWindows — 소스코드 분석]]

```
├─.github
│  └─upgrades
├─.idea
│  └─.idea.ThreeFingerDragOnWindows
│      └─.idea
├─Properties
├─ThreeFingerDragElevator
└─ThreeFingerDragOnWindows
    ├─Assets
    ├─dialogs
    ├─Properties
    ├─settings
    ├─threefingerdrag
    ├─touchpad
    └─utils
```

- `upgrades`: Github Actions
	- 워크플로, 업그레이드 스크립트
- `.idea`
	- JetBrains Rider IDE 설정 : 빌드
- `Properties`
- `ThreeFingerDragElevator`
	- 관리자 권한(elevate) 창에서 드래그가 동작하도록 하는 헬퍼
- `ThreeFingerDragOnWindows`
	- 소스코드