# 本地化

`Blockly` 支持区块本土化，在 `JSON` 区块定义对象中使用字符串表、信息字符串，来调整输入、字段、文本。

## 字符串表

`%{BKY_..}` 字符串是 `Blockly.Msg` 字符串表的一个引用。在区块初始化时， `Blockly` 会将其替换。 如 `%{BKY_LISTS_REPEAT_TITLE}` 将由 `Blockly.Msg['LISTS_REPEAT_TITLE']` 值替换。

## 信息插值

`message0` (`messageN`) 决定了输入、字段及围绕的文本。

```js
Blockly.Msg.LISTS_REPEAT_TITLE = 'create list with item %1 repeated %2 times';
```

## 重新生成字符串表

通过执行 `biuld.py` 生成字符串表，过程如下：

- 脚本根据 `msg/message.js` 中的标识符和英文译本，创建新的 `en.json` 文件
- 组合 `msg/js` 下的所有译本
- 重新生成所有语言的字符串表

