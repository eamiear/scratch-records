# 移动

主工作区可通过 滚动条、鼠标、鼠标滚轮进行移动，通过 `move` 字段进行配置。

```js
var workspace = Blockly.inject('blocklyDiv', {
  move: {
    scrollbars: true,
    drag: true,
    wheel: false
  }
});
```

- `scrollbars` - 是否展示滚动条
- `drag` - 是否可通过鼠标拖动
- `wheel` - 是否可通过鼠标滚轮滚动
