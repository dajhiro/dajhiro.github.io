모르는 거
- [x] 현재 커서 위치 단어 검색
- [ ] 폴딩

---
## Folding
생성/삭제
- `zf`
- `zd`

접기/열기
- `za`


## 현재 커서 위치의 단어 검색
- forward/backward
	- `*`
	- `#`
- 검색 결과 사이 이동
	- `n`
	- `N`
- 가장 가까운 괄호(및 괄호 짝)으로 이동
	- `%`

### 매크로
- `q{register}`: 녹화
- `@{register}`: 재생
- `@@`: 직전 매크로 재생
 
 ### 직전 편집(`Insert`) 동작 반복
- `.`

---
## Setting
### 시작 설정파일: [[PowerShell]]
- `$HOME/_vimrc`
### 현재 설정값
- `set nu`
	- 줄 번호 표시
- `set nowrap` ↔ `set wrap`
	- 자동 줄바꿈 해제
- `set tapstop=4`
	- 탭 크기 조절
	- `set shiftwidth=4`
- `set hlsearch`
	- 검색 시 하이라이트 
- `set shell=powershell`
	- `:term`시 나오는 shell을 변경하기
### 기타 설정값
- `expandtab` ↔ `noexpandtab`
	- 탭을 스페이스로 변경 

























