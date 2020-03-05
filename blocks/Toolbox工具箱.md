# Toolbox

![toolbox intro](./images/toolbox.png)

Toolbox 由XML定义，有 节点树结构或字符串形式：

节点树：

```xml
<xml id="toolbox" style="display: none">
  <block type="controls_if"></block>
  <block type="controls_whileUntil"></block>
</xml>
```

字符串形式：

```js
var toolbox = '<xml>';
  toolbox += '  <block type="controls_if"></block>';
  toolbox += '  <block type="controls_whileUntil"></block>';
  toolbox += '</xml>';
```

## 分类目录

对 区块（block） 进行分类归并，用 category 表示。

```xml
<xml id="toolbox" style="display: none">
  <category name="Control">
    <block type="controls_if"></block>
    <block type="controls_whileUntil"></block>
    <block type="controls_for">
  </category>
</xml>
```

### 属性

|名称|作用|备注|
|------|------|-----|
|colour|修改目录颜色|hue 颜色值（0-360）|
|custom|创建自定义目录/动态目录||
|expanded|是否展开嵌套目录|Boolean|

```xml
<category name="Logic" colour="210">...</category>
```

### 动态目录

可以通过 custom 属性创建动态目录。系统预留了 变量（Variable） 和 函数（function）两个分类，可在其上面添加内容或另外创建自定义分类目录。

```xml
<category name="Variables" custom="VARIABLE"></category>
<category name="Functions" custom="PROCEDURE"></category>
```

**创建步骤**

- 创建自定义目录
  
  `<category name="Colours" custom="COLOUR_PALETTE"></category>`

- 定义回调函数，并返回区块（blocks）内容
  
```js
/**
 * Construct the blocks required by the flyout for the colours category.
 * @param {!Blockly.Workspace} workspace The workspace this flyout is for.
 * @return {!Array.<!Element>} Array of XML block elements.
 */
myApplication.coloursFlyoutCallback = function(workspace) {
  // Returns an array of hex colours, e.g. ['#4286f4', '#ef0447']
  var colourList = myApplication.getPalette();
  var xmlList = [];
  if (Blockly.Blocks['colour_picker']) {
    for (var i = 0; i < colourList.length; i++) {
      var blockText = '<block type="colour_picker">' +
          '<field name="COLOUR">' + colourList[i] + '</field>' +
          '</block>';
      var block = Blockly.Xml.textToDom(blockText);
      xmlList.push(block);
    }
  }
  return xmlList;
};
```

- 在工作区（workspace)中注册回调函数

```js
myWorkspace.registerToolboxCategoryCallback(
  'COLOUR_PALETTE', myApplication.coloursFlyoutCallback);
```

### 嵌套目录

