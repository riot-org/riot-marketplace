# riot-marketplace

[Riot](https://github.com/riot-org/Riot) 的官方插件目录。仓库里只有 `marketplace.json`，每个插件自己一个 Git 仓库。

Riot 读这份清单（设置 → 插件 → 市场）。默认源是 `riot-org/riot-marketplace`。

## 上架一个插件

1. 把插件放到自己的 Git 仓库（根上有 `plugin.json` / `.claude-plugin/plugin.json` / `.cursor-plugin/plugin.json`）。
2. 给本仓库提 PR，在 `marketplace.json` 的 `plugins` 里加一条。

普通插件（clone 即装）：

```json
{
  "name": "my-linter",
  "description": "……",
  "source": { "source": "github", "repo": "you/my-linter" }
}
```

带几百 MB 二进制的插件走 Releases，`source` 写成 `archive`，`url` 指**插件仓库**的 Release，不要指本仓库。范例见现有的 `riot-plugin-doc`（仓库 [`riot-org/riot-plugin-doc`](https://github.com/riot-org/riot-plugin-doc)）。

同一作者、强绑定的一组小插件可以共一个仓库，用 `"path": "plugins/foo"`。

没进这份目录的人，对方仍可在 Riot 里「从 Git 安装」，或在市场列表里加自己的 `owner/repo`。

## 现有的插件

| 插件 | 仓库 | 内容 |
| --- | --- | --- |
| `riot-plugin-doc` | [riot-plugin-doc](https://github.com/riot-org/riot-plugin-doc) | Word / Excel / PPT / PDF。仓库是源码，安装包走 Releases |
