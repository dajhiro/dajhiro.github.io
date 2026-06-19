vimrc 적용 명령어
`:source %`

Command Mode
`%`는 현재 파일

`set nu`
  `set nonu`


windows powershell vimrc 위치와 tab 크기 설정하기

기본 하이라이트가 사라졌다. 원래 vimrc 파일은 어디있나?
```powershell
vi $HOME/_vimrc
```

기본 vimrc 파일을 불러오기
```vim
if filereadable($VIMRUNTIME . '/defaults.vim')
  unlet! g:skip_defaults_vim
  source $VIMRUNTIME/defaults.vim
endif
```

PowerShell에서의 Space 처리는 "(쌍따옴표) 말고는 불가한가?
Backtick`` ` ``: the escape sequence of PowerShell

Backtick 한개만 마크다운에서 표현하는 방법 
`` ` ``

---
`ta`, `fa`
move the cursor to the next occurence of a specified character on the ==same line==.



