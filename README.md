# javascript_projects

零散 JavaScript / 网页小工具。浏览器直接打开，不依赖构建。

## 目录

```text
utils/
  excel转JavaScript数组/     # Excel → 控制台里的 JS 数组字面量
```

## 用法

### Excel 转 JavaScript 数组

1. 浏览器打开 `utils/excel转JavaScript数组/程序.html`；
2. 选择 Excel 文件，页面读出工作表内容；
3. 按 `F12` 打开控制台，复制打印出来的数组；
4. 粘到目标项目的源码里。

`xlsx.core.min.js` 是随页面一起分发的 SheetJS 运行时，必须和 `程序.html` 放在同一目录。

## 别的东西在哪

Excel 转 enazo 题库、Bangumi 收藏拉取、词库合并与上传，都在
[bangumi_to_enazos_seele](https://github.com/Kflho/bangumi_to_enazos_seele)：

- 网页版转换页在那边 `src/web/convert.html`；
- 词库格式规范在那边 `bin/requirements/enazo-词库格式.md`；
- Bangumi 收藏导 Excel 用 [gm_scripts](https://github.com/zhifengle/gm_scripts) 的脚本。

本仓库只留和 enazo 无关的通用小工具。

## 已知限制

- 页面在本地处理文件，不上传、不联网；
- 没有自动化测试，改动靠拿一份表格跑一遍核对。

## License

仅供个人使用。
