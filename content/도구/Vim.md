모르는 거
- [x] 현재 커서 위치 단어 검색
- [x] 기능: 폴딩
- [x] 명령어: `autocmd`

---
## command mode 명령어, [[250813(수)]], 14:49
- `t`: 복사
	- `:1,3t9`
		- 1~3번째 줄을 9번째 줄 아래에 붙여넣기
- `m`: 이동(move)
	- `:1,5m.`
		- 1~5번째 줄을 현재 위치 아래로 이동
- `r`: 읽기(read)
	- `:0r {path}`
		- 0번째 줄 아래에서 `{path}`의 파일을 읽어서 붙여넣기
			- 0번째가 존재하긴 하는구나?
- `![command]`: 쉘 명령어 실행
- `g`
	- `:g/{pattern}/d`
		- `//d`: 제거
- `normal {commands}`
	- `:normal '<,'> dd`
		- `'<,'>` 선택 영역



와 근데 함수들도 명령어에서 합칠 수 있구나...
`.` 문자열 사이를 연결해주는 역할 (`+`와 비슷함)

함수: `expand()`
- **기능**: 문자열 패턴을 확장하여 파일 이름, 경로, 환경 변수 등 정보를 가져옵니다.
- **예시**:
    - `expand('%')` : 현재 버퍼의 전체 파일 경로
    - `expand('%:t')` : 현재 파일 이름만 (경로 제외)
    - `expand('%:t:r')` : 확장자 제외한 파일 이름만

## 명령어: `autocmd`, [[250813(수)]], 14:49
어떤 파일들에 대해서 이벤트 값 발생시 명령어들을 자동으로 실행
### `autocmd`: 폴딩 상태 자동 저장/불러오기

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

### `autocmd`: 템플릿 만들기
```vim
" ~/_vimrc
augroup Template
	autocmd!
	autocmd BufNewFile *.cs execute '0r ~/vimfiles/templates/template.cs' | execute '%s/NewFile/' . expand('%:t:r') . '/g'
augroup END
```
`autocmd BufNewFile *.cs`
- **`autocmd`**: 자동 명령어(autocommand)를 등록하는 명령입니다.
- **`BufNewFile`**: 새로 생성한 버퍼(파일)가 열릴 때 발생하는 이벤트입니다.
- **`*.cs`**: `.cs` 확장자를 가진 파일에만 적용합니다.

즉, **새로 만드는 C# 파일에 대해 자동으로 명령을 실행하라**는 뜻입니다.

---

`execute '0r ~/vimfiles/templates/template.cs'`
- **`execute`**: 문자열로 된 Vim 명령어를 실행합니다.
- **`0r`**: 커서를 0번(첫 번째) 줄로 이동한 뒤, 그 위치에 파일 내용을 읽어들여 삽입하는 명령(`r` = read)입니다.
- **`~/vimfiles/templates/template.cs`**: 읽어들일 템플릿 파일 경로입니다.

즉, 새 `.cs` 파일을 만들면 템플릿 파일 내용을 **버퍼 맨 위에 삽입**합니다.

---
- `|`
	- 명령어 구분자입니다.
	- 앞 명령어가 끝난 뒤에 이어서 다음 명령어를 실행하게 합니다.

---

`execute '%s/NewFile/' . expand('%:t:r') . '/g'`
- 다시 `execute`를 사용해 substitution(치환) 명령을 실행합니다.
- `%s/.../.../g`는 현재 버퍼 전체(`%`)에서 문자열을 찾아서 교체하는 명령입니다.
- **찾는 문자열**: `NewFile` (템플릿에 적힌 플레이스홀더)
- **교체할 문자열**: `expand('%:t:r')`

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

























