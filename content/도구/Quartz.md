## 거지같은거
- 제목 없애버리고 싶은데 못한다는거
	- 뭔 Title보다 H1이 더 크냐? 장난함?

---
## 트러블 슈팅
### `index.md` 대신에 `Index.md`가 있으면 꼬여버린다(대소문자 구분)
이거때문에 1시간을 그냥 버림

### `git reset --hard`를 하니 폴더 연결이 끊겨버림(심볼릭 링크)
어떻게 복구하는지 알아볼 시간에 처음부터 다시 세팅하는게 더 나을 거 같아서 안 찾아봄

ChatGPT 따라하다가 시간 다버림
근데 이렇게 만들어 놓았다 한들 쓰긴 쓰려나? 아무래도 호스팅이 되니 나쁘지는 않은듯
구글 검색에 뜨게 만들고 싶은데 그런 방법이 있을까?

---
## 절차
`npx quartz create`
- 연결하기
	- `git reset` 과정에서 연결이 끊겨버렸다

`git remote set-url origin [My Repository]`
- 내 저장소 연걸하기

`npx quartz sync`
 
 `vi .github/workflows/deploy.yml`

## ColorScheme
Gold
- secondary: `#edbb00`
- territory: `#ffcc11`

```ts
// 
#a0d08b
#c5e4a8
```

```ts
// quartz.config.ts
import { QuartzConfig } from "./quartz/cfg"
import * as Plugin from "./quartz/plugins"

/**
 * Quartz 4 Configuration
 *
 * See https://quartz.jzhao.xyz/configuration for more information.
 */
const config: QuartzConfig = {
  configuration: {
    pageTitle: "hirodev",
    pageTitleSuffix: "",
    enableSPA: true,
    enablePopovers: true,
    analytics: {
      provider: "plausible",
    },
    locale: "ko-KR",
    baseUrl: "hiro-jeon.github.io/quartz/",
    ignorePatterns: ["private", "templates", ".obsidian"],
    defaultDateType: "modified",
    theme: {
      fontOrigin: "googleFonts",
      cdnCaching: true,
      typography: {
        header: "Schibsted Grotesk",
        body: "Source Sans Pro",
        code: "IBM Plex Mono",
      },
      colors: {
        lightMode: {
          light: "#faf8f8",
          lightgray: "#e5e5e5",
          gray: "#b8b8b8",
          darkgray: "#4e4e4e",
          dark: "#2b2b2b",
          secondary: "#a0d08b",
          tertiary: "#c5e4a8",
          highlight: "rgba(143, 159, 169, 0.15)",
          textHighlight: "#fff23688",
        },
        darkMode: {
          light: "#161618",
          lightgray: "#393639",
          gray: "#646464",
          darkgray: "#d4d4d4",
          dark: "#ebebec",
          secondary: "#a0d08b",
          tertiary: "#c5e4a8",
          highlight: "rgba(143, 159, 169, 0.15)",
          textHighlight: "#b3aa0288",
        },
      },
    },
  },
  plugins: {
    transformers: [
      Plugin.FrontMatter(),
      Plugin.CreatedModifiedDate({
        priority: ["frontmatter", "git", "filesystem"],
      }),
      Plugin.SyntaxHighlighting({
        theme: {
          light: "github-light",
          dark: "github-dark",
        },
        keepBackground: false,
      }),
      Plugin.ObsidianFlavoredMarkdown({ enableInHtmlEmbed: false }),
      Plugin.GitHubFlavoredMarkdown(),
      Plugin.TableOfContents(),
      Plugin.CrawlLinks({ markdownLinkResolution: "shortest" }),
      Plugin.Description(),
      Plugin.Latex({ renderEngine: "katex" }),
    ],
    filters: [Plugin.RemoveDrafts()],
    emitters: [
      Plugin.AliasRedirects(),
      Plugin.ComponentResources(),
      Plugin.ContentPage(),
      Plugin.FolderPage(),
      Plugin.TagPage(),
      Plugin.ContentIndex({
        enableSiteMap: true,
        enableRSS: true,
      }),
      Plugin.Assets(),
      Plugin.Static(),
      Plugin.Favicon(),
      Plugin.NotFoundPage(),
      // Comment out CustomOgImages to speed up build time
      Plugin.CustomOgImages(),
    ],
  },
}

export default config

```

---
참조
- [[Obsidian]]