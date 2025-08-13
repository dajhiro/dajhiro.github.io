모르는 거
- [x] 현재 커서 위치 단어 검색
- [ ] 폴딩

---
## autocmd
어떤 파일들에 대해서 이벤트 값 발생시 명령어들을 자동으로 실행
### 폴딩 상태 자동 저장/불러오기

```vim
" ~/_vimrc
autocmd BufWinEnter * silent! loadview
autocmd BufWinLeave * mkview
```
- **`autocmd`**: 자동 명령어(autocommand)를 정의하는 키워드입니다.
- **`BufWinEnter`**: 버퍼(Buffer)가 윈도우(Window)에 표시될 때 발생하는 이벤트입니다.
- **`*`**: 모든 파일 이름에 대해 적용합니다.
- **`silent!`**: 명령 실행 시 에러 메시지 등을 표시하지 않도록 합니다.
- **`loadview`**: 현재 버퍼에 저장된 뷰 정보를 불러옵니다. (커서 위치, 접기 상태, 창 크기 등)

즉, 다음과 같다
```vim
autocmd [event] [file] [command]
```

### 템플릿 만들기

```vim
" ~/_vimrc

augroup Template
	autocmd!
	autocmd BufNewFile *.cs 0r ~/vimfile/templates/template.cs
augroup END
```



---
## 기능: Folding
명령어
`:mkview` 폴드 상태 생성
`:loadview` 폴드 상태 불러오기

생성/삭제
- `zf`
- `zd`

접기/열기
- 토글: `za`
- 접기: `zc`
- 열기: `zo`

전부 접기/열기
- `zM`
	- Minimize
- `zR`
	- Reveal


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

























