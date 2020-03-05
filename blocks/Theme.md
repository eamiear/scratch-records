# 主题

## 区块样式

区块样式由四个变量组成：

|属性名|必须|说明||
|------|--|---|---|
|colourPrimary|必须|区块背景色|hex\hue|
|colourSecondary|可选|阴影区块（shadow block）颜色|hex|
|colourTertiary|可选|区块边框色|hex|
|hat|可选|为区块添加"帽子"|`cap`|

## 分类样式

|属性名|必须|说明||
|------|--|---|---|
|colour|必须|分类样式，该值应该与colourPrimary一致|hex\hue|

## 使用主题

- 创建主题

// 定义区块样式

```js
Blockly.Themes.Dark = {};

Blockly.Themes.Dark.defaultBlockStyles = {
  "colour_blocks": {
    "colourPrimary": "#a5745b",
    "colourSecondary": "#dbc7bd",
    "colourTertiary": "#845d49"
  },
  "list_blocks": {
    "colourPrimary": "#745ba5",
    "colourSecondary": "#c7bddb",
    "colourTertiary": "#5d4984"
  }
};
```

// 定义分类样式

```js
Blockly.Themes.Dark.categoryStyles = {
  "colour_category": {
    "colour": "#a5745b"
  },
  "list_category": {
    "colour": "#745ba5"
  }
};
```

// 创建主题

```js
Blockly.Themes.Dark =
    new Blockly.Theme('dark', Blockly.Themes.Dark.defaultBlockStyles,
        Blockly.Themes.Dark.categoryStyles);
```

// 设置组件样式

```js
Blockly.Themes.Dark.setComponentStyle('workspaceBackgroundColour', '#1e1e1e');
Blockly.Themes.Dark.setComponentStyle('toolboxBackgroundColour', '#333');
Blockly.Themes.Dark.setComponentStyle('toolboxForegroundColour', '#fff');
Blockly.Themes.Dark.setComponentStyle('flyoutBackgroundColour', '#252526');
Blockly.Themes.Dark.setComponentStyle('flyoutForegroundColour', '#ccc');
Blockly.Themes.Dark.setComponentStyle('flyoutOpacity', 1);
Blockly.Themes.Dark.setComponentStyle('scrollbarColour', '#797979');
Blockly.Themes.Dark.setComponentStyle('scrollbarOpacity', 0.4);
```

[`Reference Dark Theme`](https://github.com/google/blockly/blob/master/core/theme/dark.js)

- 添加样式名

// 分类

```xml
<category name="Logic" categorystyle="logic_category">
</category>
```

// 区块

```js
Blockly.Blocks['string_length'] = {
  init: function() {
    this.jsonInit({
      "message0": 'length',
      ],
      "output": "Number",
      "style":"logic_blocks"
    });
  }
};
```

- 应用主题

1. 在 Blockly Options 中设置

// 主题对象

```js
{
    theme: new Blockly.Theme('themeName', blockStyles, categoryStyles)
}
```

// JSON

```js
{
   theme: {
      'blockStyles' : {
         "list_blocks": {
            "colourPrimary": "#4a148c",
            "colourSecondary":"#AD7BE9",
            "colourTertiary":"#CDB6E9"
         }
      },
      'categoryStyles' : {
         "list_category": {
            "colour": "#4a148c"
         }
      },
      'componentStyles' : {
         'workspaceBackgroundColour': '#1e1e1e'
      }
   }
}
```

2. 动态设置

调用

`yourWorkspace.setTheme(theme)`

## 脚本创建主题

[`theme_scripts`](https://github.com/google/blockly/tree/master/theme_scripts)
