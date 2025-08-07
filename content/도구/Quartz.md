- [[Obsidian]]
- [공식 홈페이지](https://quartz.jzhao.xyz/)
---
## Custom css
나의 첫번째 css 커스터마이징
체크박스는 체크 안하도록 해결!
```scss
@use "./base.scss";

// 체크된 체크박스 있는 리스트 항목 스타일 덮어쓰기
li:has(> input[type="checkbox"]:checked) {
  text-decoration: none;
  color: white;
}
```

시팔 안되네
## 트러블 슈팅
### `index.md` 대신에 `Index.md`가 있으면 꼬여버린다(대소문자 구분)
이거때문에 1시간을 그냥 버림

### `git reset --hard`를 하니 폴더 연결이 끊겨버림(심볼릭 링크)
어떻게 복구하는지 알아볼 시간에 처음부터 다시 세팅하는게 더 나을 거 같아서 안 찾아봄

ChatGPT 따라하다가 시간 다버림
근데 이렇게 만들어 놓았다 한들 쓰긴 쓰려나? 아무래도 호스팅이 되니 나쁘지는 않은듯
구글 검색에 뜨게 만들고 싶은데 그런 방법이 있을까?

결국 겁나 많이 쓰고 있다.

---
## 절차
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


## ColorScheme
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

---
참조
- [[Obsidian]]
- [[chokidar]]