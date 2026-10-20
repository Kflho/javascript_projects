# javascript_projects

零散 JavaScript / 网页小工具的集合。目前只有 `utils/` 下的两个单页工具，都是给别的项目准备数据用的，不依赖构建、直接浏览器打开。

## 目录

```text
utils/
  excel转JavaScript数组/     # Excel → 控制台里的 JS 数组字面量
  excel转enazo题库/          # Excel → enazo 题库行（中文名,日文名$备注）
```

## 用法

### Excel 转 JavaScript 数组

1. 浏览器打开 `utils/excel转JavaScript数组/程序.html`；
2. 选择 Excel 文件，页面读出工作表内容；
3. 按 `F12` 打开控制台，复制打印出来的数组；
4. 粘到目标项目的源码里。

`xlsx.core.min.js` 是随页面一起分发的 SheetJS 运行时，必须和 `程序.html` 放在同一目录。

### Excel 转 enazo 题库

1. 浏览器打开 `utils/excel转enazo题库/convert.html`；
2. 选择 Excel 文件，页面直接给出转换结果；
3. 点「下载 output.txt」，或从页面复制。

输出是每行一条题库：

```text
中文名,日文名$备注
```

没有备注的行只输出 `中文名,日文名`。目录里的 `megumin.txt` 和 `output (1).txt` 是一份输入输出示例。

## 已知限制

- 两个页面都在浏览器本地处理文件，不上传、不联网；
- 没有构建和测试，改动直接在浏览器里验证；
- 表格列顺序按页面里的约定读，换表格结构要先改页面代码。

## License

仅供个人使用。
