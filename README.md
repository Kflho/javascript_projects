# javascript_projects

零散 JavaScript / 网页小工具的集合。两个 Excel 工具都在浏览器本地跑，不依赖构建，打开就能用。

## 目录

```text
utils/
  excel转JavaScript数组/     # Excel → 控制台里的 JS 数组字面量
  excel转enazo题库/          # Excel → enazo 词库行（格式规范的单一来源）
```

## 用法

### Excel 转 JavaScript 数组

1. 浏览器打开 `utils/excel转JavaScript数组/程序.html`；
2. 选择 Excel 文件，页面读出工作表内容；
3. 按 `F12` 打开控制台，复制打印出来的数组；
4. 粘到目标项目的源码里。

`xlsx.core.min.js` 是随页面一起分发的 SheetJS 运行时，必须和 `程序.html` 放在同一目录。

### Excel 转 enazo 题库

浏览器打开 `utils/excel转enazo题库/convert.html`，选一个 xlsx，页面直接给出结果，
可以复制或下载。全程本地处理，不联网。

输入列是 `名称`、`别名`、`吐槽`，转换规则：

- 名称和别名里的 `,` `，` `、` `;` `；` `/` 和空格换成 `-`（这些是 enazo 的切割符）；
- `吐槽` 按换行拆成多条评论，用逗号并列放在 `$` 后面，不会粘成一句；
- 同名条目合并成一条，别名取并集；
- 每行一条 `名称,别名一,别名二$评论`，直接粘进 enazo 的「批量新建」。

词库格式规范见 `utils/excel转enazo题库/bin/references/enazo-词库格式.md`，
这是全流程共用的单一来源；页面里的转换规则按它实现。

## 依赖关系

本仓库只负责「格式规范」和「本地小工具」，不联网。

| 环节 | 谁来做 | 说明 |
|---|---|---|
| Bangumi 收藏 → Excel | [gm_scripts](https://github.com/zhifengle/gm_scripts) 的导出脚本 | 别人维护的浏览器脚本，本仓库不重复实现 |
| Excel → 词库行 | 本仓库 `convert.html` | 纯本地，适合小批量、没网的时候 |
| 拉收藏、多人合并、补别名、上传词库 | [bangumi_to_enazos_seele](https://github.com/Kflho/bangumi_to_enazos_seele) | 走 Bangumi 与 enazo 接口的完整流程，词库格式实现也在这边 |

需要「全量、增量、合并、优化、直接管理 enazo 词库」时去 enazo 项目；只想把一份表格
转成录入格式，用这个页面就够了。

## 已知限制

- 两个页面都在本地处理文件，不上传、不联网；
- `convert.html` 的表头按 `名称/别名/吐槽` 认，换列名要改页面里的字段名；
- 没有自动化测试，改动靠拿一份表格跑一遍核对。

## License

仅供个人使用。
