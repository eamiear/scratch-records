# 工作区网格

工作区网格配置

```js
var workspace = Blockly.inject('blocklyDiv', {
  toolbox: document.getElementById('toolbox'),
  grid: {
    spacing: 20,
    length: 3,
    colour: '#ccc',
    snap: true
  }
});
```

|属性名|说明|备注|
|------|---|---|
|spacing|网格点间隔||
|length|网格点尺寸||
|colour|网格点颜色|hex/rgb|
|snap|是否捕捉网格点|boolean|
