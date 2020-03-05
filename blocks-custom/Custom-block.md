# Custom Blocks

区块定义由三部分组成：

- 区块定义对象： 定义区块外观和行为，包括文本、颜色、变量域和连接

- 工具箱引用： 工具箱 `XML` 引入区块

- 生成函数： 生成区块代码

## 区块定义

// 格式

```js
Blockly.Blocks['string_length'] = {
  init: function() {
    this.jsonInit({
    });
  }
};
```

- `string_length`: 区块类型名称
- `init`: 定义区块外观

## 工具箱引入

区块定义完后，通过类型名称引入到工具箱中

```xml
<xml id="toolbox" style="display: none">
  <category name="Text">
    <block type="string_length"></block>
  </category>
  ...
</xml>
```

## 添加生成函数

```js
Blockly.JavaScript['text_length'] = function(block) {
  // String or array length.
  var argument0 = Blockly.JavaScript.valueToCode(block, 'VALUE',
      Blockly.JavaScript.ORDER_FUNCTION_CALL) || '\'\'';
  return [argument0 + '.length', Blockly.JavaScript.ORDER_MEMBER];
};
```
