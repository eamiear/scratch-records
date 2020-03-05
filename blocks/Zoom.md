# 工作区控制器 `zoom`

通过 `zoom` 配置工作区的控制操作

```js
var workspace = Blockly.inject('blocklyDiv', {
  toolbox: document.getElementById('toolbox'),
  zoom: {
    controls: true,
    wheel: true,
    startScale: 1.0,
    maxScale: 3,
    minScale: 0.3,
    scaleSpeed: 1.2
  },
});
```

|属性名|说明|备注|
|------|---|---|
|controls|是否显示 居中、放大、缩小按钮||
|wheel|是否允许鼠标滚轮控制放大缩小||
|startScale|||
|maxScale|||
|minScale|||
|scaleSpeed|||
