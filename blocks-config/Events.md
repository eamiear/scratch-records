# 事件

工作区每发生一次变化都会触发一个事件

## 事件监听方法

- `addChangeListener`： 添加监听事件
- `removeChangeListener`： 移除监听事件

```js
workspace.addChangeListener(fn)
workspace.removeChangeListener(fn)
```

另外，`block` 区块可定义 `onchagne` 方法监听工作区的变化。

## 事件类型

事件共享的属性：

|属性名|类型|说明|
|------|---|---|
|type|string|Blockly.Events.CREATE, Blockly.Events.DELETE, Blockly.Events.CHANGE, Blockly.Events.MOVE, Blockly.Events.UI|
|workspaceId|string|工作区UUID|
|blockId|string|区块UUID|
|group|string|分组UUID|

### `Blockly.Events.BLOCK_CREATE`

额外属性

|属性名|类型|说明|
|------|---|---|
|xml|object|区块XML树|
|ids|array|区块UUID数组|

### `Blockly.Events.BLOCK_DELETE`

额外属性

|属性名|类型|说明|
|------|---|---|
|oldXml|object|区块XML树|
|ids|array|区块UUID数组|

### `Blockly.Events.BLOCK_CHANGE`

额外属性

|属性名|类型|说明|
|------|---|---|
|element|string|`field/comment/collapsed/disabled/inline/mutate`|
|name|string|变量名|
|oldValue|value|原始值|
|newValue|value|变更值|

### `Blockly.Events.BLOCK_MOVE`

额外属性

|属性名|类型|说明|
|------|---|---|
|oldParentId|string||
|oldInputName|string||
|oldCoordinate|object||
|newParentId|string||
|newInputName|string||
|newCoordinate|object||

### `Blockly.Events.VAR_CREATE`

额外属性

|属性名|类型|说明|
|------|---|---|
|varType|string||
|varName|string||
|varId|string||

### `Blockly.Events.VAR_DELETE`

额外属性

|属性名|类型|说明|
|------|---|---|
|varType|string||
|varName|string||
|varId|string||

### `Blockly.Events.VAR_RENAME`

额外属性

|属性名|类型|说明|
|------|---|---|
|oldName|string||
|newName|string||
|varId|string||

### `Blockly.Events.UI`

额外属性

|属性名|类型|说明|
|------|---|---|
|element|string|`selected\category\click\commentOpen\mutatorOpen\warningOpen\theme`|
|oldValue|value||
|newValue|value||
