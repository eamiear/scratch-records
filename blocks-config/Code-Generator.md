# 代码生成器

将 积木应用 转为 程序编码

## 生成代码

- 引入 程序生成器 脚本

```html
<script src="blockly_compressed.js"></script>
<script src="javascript_compressed.js"></script>
```

- 调用生成方法

```js
var code = Blockly.JavaScript.workspaceToCode(workspace);
```

## 实时生成代码

工作区（`workspace`）监听积木变化，实时导出代码。

```js
function myUpdateFunction(event) {
  var code = Blockly.JavaScript.workspaceToCode(workspace);
  document.getElementById('textarea').value = code;
}
workspace.addChangeListener(myUpdateFunction);
```
