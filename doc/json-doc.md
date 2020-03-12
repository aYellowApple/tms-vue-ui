# json 文档编辑器（json-doc）

根据指定的`JSONSchema`编辑 json 数据。

## 属性（props）

通过组件调用时，支持以下 Props：

| 参数           | 说明                             | 类型    | 默认值 |
| -------------- | -------------------------------- | ------- | ------ |
| schema         | JSONSchema 定义                  | Object  | -      |
| value          | 要编辑的 json 文档对象           | Object  | -      |
| fieldWrapClass | 输入控件的包裹类                 | String  | -      |
| requireButtons | 是否显示表单操作按钮，例如：提交 | Boolean | true   |
| oneWay         | 传入数据是单向的，不会被修改     | Boolean | true   |

必须传入`schema`对象。支持`v-model`传递要编辑的 json 文档。

## 方法

| 名称    | 说明             | 参数                                                      |
| ------- | ---------------- | --------------------------------------------------------- |
| editing | 返回表单中的数据 | isCheckValidity，返回前是否做合规性检查，不合规返回 false |
| reset   | 恢复数据原始值   | -                                                         |

## 事件

通过组件调用时，支持以下事件：

| 名称   | 说明                   | 参数 |
| ------ | ---------------------- | ---- |
| submit | 选择表单的提交按钮时。 | -    |

参考：https://json-schema.org

## 定制（setComponent 方法）

使用`setComponent`方法替换组件。

| 参数           | 说明                                                              | 类型     | 默认   |
| -------------- | ----------------------------------------------------------------- | -------- | ------ |
| type           | 控件名称                                                          | String   | -      |
| tag            | 组件名称，例如：`el-input`等                                      | String   | -      |
| options        | 传入 `createElement` 函数的组件选项                               | Object   | 空对象 |
| options.native | true 将指定的值添加到`attrs`否则添加到`props`                     | Boolean  | 空对象 |
| options        | 指定为一个函数，将被调用，传入参数`{vm,field,item}`，返回属性设置 | Function | -      |

支持设置的控件及组件：

| 控件名称      | 说明                     | 默认组件 |
| ------------- | ------------------------ | -------- |
| title         | JSONSchema.\$title       | h1       |
| description   | JSONSchema.\$description | p        |
| error         | 错误提示                 | div      |
| form          | -                        | form     |
| label         | -                        | label    |
| input         | -                        | input    |
| textarea      | -                        | textarea |
| radio         | 定义中出现`oneOf`时      | input    |
| radiogroup    | -                        | div      |
| select        | 定义中包含`enum:[]`      | select   |
| option        | select 控件中的选项      | option   |
| checkbox      | -                        | input    |
| checkboxgroup | -                        | div      |
| file          | -                        | input    |
| button        | -                        | div      |
| jsondoc       | -                        | div      |

## 嵌套使用 json-doc

## 返回数据的方式

## json 文档编辑器（element-ui 版）

```js
import { ElJsonDoc } from 'tms-vue-ui'
```

```html
<tms-el-json-doc :schema="schema" :doc="doc" v-on:submit="jsonDocSubmit"></tms-el-json-doc>
```