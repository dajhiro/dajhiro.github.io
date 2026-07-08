# Sample Plugin
## 정보
### 링크
GitHub: []
Guide:
- [Build a plugin - Developer Documentation](https://docs.obsidian.md/Plugins/Getting+started/Build+a+plugin)
- [Submit your plugin - Developer Documentation](https://docs.obsidian.md/Plugins/Releasing/Submit+your+plugin#Prerequisites)

### 학습 목표
- Configure an environment for developing Obsidian plugins
- Compile a plugin from source code
- Reload a plugin after making change to it


## 목차
1. [[#Build the plugin]]
2. [[#Update the plugin manifest]]
3. [[#Update the source code]]
4. [[#Hot Reload]]

## Build the plugin

```sh
npm install # 1. Install dependencies.
npm run dev # 2. Compile the source code. And keeps running in the terminal and rebuilds the plugin when you modify the source code.
```

## Update the plugin manifest
`manifest.json`
```json
{
  "id": "my-homepage",
  "name": "My Homepage"
}
```

적용: 저장 후에, restart 근데 새로고침하니 되긴함

## Update the source code
`main.ts`
```ts
import { Notice, Plugin } from 'obsidian';

export default class MyHomepage extends Plugin {
  async onLoad() {
    this.addRibbonIcon('dice', 'Greet', () => {
      new Notice('Hello, world!');
    }); // Plugin.addRibbonIcon()
  }
}
```

적용: 저장 후 **Reload app without saving**

## Hot Reload
[pjeby/hot-reload: Automatically reload Obsidian plugins in development when their files are changed](https://github.com/pjeby/hot-reload)
커뮤니티 플러그인을 설치하니 문제 없음


