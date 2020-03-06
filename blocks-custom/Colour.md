# 颜色

## 颜色引用

`Blockly` 内置九种颜色常量，这些颜色值可用于 JSON 定义和Javascript中：

```
'%{BKY_LOGIC_HUE}'
'%{BKY_LOOPS_HUE}'
'%{BKY_MATH_HUE}'
'%{BKY_TEXTS_HUE}'
'%{BKY_LISTS_HUE}'
'%{BKY_COLOUR_HUE}'
'%{BKY_VARIABLES_HUE}'
'%{BKY_VARIABLES_DYNAMIC_HUE}'
'%{BKY_PROCEDURES_HUE}'
```

## 添加颜色常量

在 `Blockly.Msg` 中添加颜色常量：

```js
// Define the colour
Blockly.Msg.EVERYTHING_HUE = 42;
// Use in a block or block definition:
block.setColour('%{BKY_EVERYTHING_HUE}');
```

## 在 Toolbox XML 中使用

```xml
<category name="Logic" colour="%{BKY_LOGIC_HUE}">
  ...
</category>
```
