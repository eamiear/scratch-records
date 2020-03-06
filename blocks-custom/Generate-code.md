# 生成代码

如何为自定义区块添加代码生成器。

## 添加代码生成器

在 `generators/` 目录下选择待生成的语言版本，典型的区块代码生成器如下：

```js
Blockly.JavaScript['text_indexOf'] = function(block) {
  // Search the text for a substring.
  var operator = block.getFieldValue('END') == 'FIRST' ? 'indexOf' : 'lastIndexOf';
  var subString = Blockly.JavaScript.valueToCode(block, 'FIND',
      Blockly.JavaScript.ORDER_NONE) || '\'\'';
  var text = Blockly.JavaScript.valueToCode(block, 'VALUE',
      Blockly.JavaScript.ORDER_MEMBER) || '\'\'';
  var code = text + '.' + operator + '(' + subString + ')';
  return [code, Blockly.JavaScript.ORDER_MEMBER];
};
```

## 获取参数

生成器有三个方法来接收参数和字段数据。

### `getFieldValue`

根据字段名称获取字段值

```js
block.getFieldValue('END')
```

### `valueToCode`

### `statementToCode`

[`Reference: Generating Code`](https://developers.google.com/blockly/guides/create-custom-blocks/generating-code)
