Meta
- Prev: [[Plugin — Sample plugin]]
- Next: 

---
# Anatomy of a plugin
The `Plugin` class
the lifecycle of a plugin and exposes the operations available to all plugins

```ts
import { Plugin } from 'obsidian';

export default class ExamplePlugin extends Plugin {
  async onload() {
    // Configure resources needed by the plugin.
  }
  
  async onunload() {
    // Release any resources configured by the plugin.
  }
}
```