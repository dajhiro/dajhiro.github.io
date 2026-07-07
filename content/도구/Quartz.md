- [공식 홈페이지](https://quartz.jzhao.xyz/)
---
## 개선 사항
- [x] ⇒ [[Quartz]]: [[스케줄러|윈도우 스케줄러]] 자동 싱크 완료
	- 문제: 반영이 너무 느리고 번거롭다. 특히 설정값이. 자동으로 반영만 된다면 훨씬 좋을텐데... 윈도우에는 [[스케줄러]]가 없나?
	- ~~[[../../게임 프로젝트/chokidar]]: 실패~~

---
## 구동
### 바로 빌드해서 확인해보기
다음 명령어 입력 후 `localhost:8080`에 접속하면 확인 가능
```powershell
npx quartz build --serve
```

## CSS
나의 첫번째 CSS 커스터마이징.
체크박스에 삭제선 설정 안하도록 해결!
글자색도 다른 `body`와 똑같이 즉 `inherited`
```scss
@use "./base.scss";

// 체크된 체크박스 있는 리스트 항목 스타일 덮어쓰기
.pages article li:has(> input[type="checkbox"]:checked) {
  text-decoration: none;
  color: inherited;
}
```

- [x] 시팔 안되네: 해결!
	- `.pages article` 등 클래스, 태그가 적용된 것이 CSS 상에서 우선순위를 가짐

---
## 초기 세팅
`npx quartz create`
- 연결하기
	- `git reset` 과정에서 연결이 끊겨버렸다

`git remote set-url origin [My Repository]`
- 내 저장소 연걸하기

`vi .github/workflows/deploy.yml`
`npx quartz sync`
 
- 제목 없애버리고 싶은데 못한다는거
	- 뭔 Title보다 H1이 더 크냐? 장난함?
	- ⇒ 생각보다 괜찮은 것 같기도...

## 초기 세팅: 트러블 슈팅
### `index.md` 대신에 `Index.md`가 있으면 꼬여버린다(대소문자 구분)
이거때문에 1시간을 그냥 버림

### `git reset --hard`를 하니 폴더 연결이 끊겨버림(심볼릭 링크)
어떻게 복구하는지 알아볼 시간에 처음부터 다시 세팅하는게 더 나을 거 같아서 안 찾아봄

ChatGPT 따라하다가 시간 다버림
근데 이렇게 만들어 놓았다 한들 쓰긴 쓰려나? 아무래도 호스팅이 되니 나쁘지는 않은듯
구글 검색에 뜨게 만들고 싶은데 그런 방법이 있을까?
- ⇒ 결국 겁나 많이 쓰고 있다.

---
## CSS
### ColorScheme
- [[quartz.config.ts]]
```ts
// Currnet
#a0d08b
#c5e4a8
```

``` ts
// Gold
#edbb00
#ffcc11
```

























