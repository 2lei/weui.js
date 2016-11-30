## Functions

<dl>
<dt><a href="#picker">picker(items, options)</a></dt>
<dd><p>picker 多列选择器。</p>
</dd>
<dt><a href="#datePicker">datePicker(options)</a></dt>
<dd><p>dataPicker 时间选择器，由picker拓展而来，提供年、月、日的选择。</p>
</dd>
</dl>

<a name="picker"></a>

## picker(items, options)
picker 多列选择器。

**Kind**: global function  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| items | <code>array</code> |  | picker的数据，即用于生成picker的数据，picker的层级可以自己定义，但建议最多三层。数据格式参考example。 |
| options | <code>Object</code> |  | 配置项 |
| [options.id] | <code>string</code> | <code>&quot;default&quot;</code> | 作为picker的唯一标识 |
| [options.onChange] | <code>function</code> |  | 在picker选中的值发生变化的时候回调 |
| [options.onConfirm] | <code>function</code> |  | 在点击"确定"之后的回调。回调返回选中的结果(Array)，数组长度依赖于picker的层级。 |

**Example**  
```js
// 单列picker
weui.picker([
{
    label: '飞机票',
    value: 0,
    disabled: true // 不可用
},
{
    label: '火车票',
    value: 1
},
{
    label: '汽车票',
    value: 3
},
{
    label: '公车票',
    value: 4,
}
], {
   onChange: function (result) {
       console.log(result)
   },
   onConfirm: function (result) {
       console.log(result)
   },
   id: 'singleLinePicker'
});
```
**Example**  
```js
// 多列picker
weui.picker([
{
    label: '飞机票',
    value: 0,
    children: [
        {
            label: '经济舱',
            value: 1
        },
        {
            label: '商务舱',
            value: 2
        }
    ]
},
{
    label: '火车票',
    value: 1,
    children: [
        {
            label: '卧铺',
            value: 1,
            disabled: true // 不可用
        },
        {
            label: '坐票',
            value: 2
        },
        {
            label: '站票',
            value: 3
        }
    ]
},
{
    label: '汽车票',
    value: 3,
    children: [
        {
            label: '快班',
            value: 1
        },
        {
            label: '普通',
            value: 2
        }
    ]
}
], {
   onChange: function (result) {
       console.log(result)
   },
   onConfirm: function (result) {
       console.log(result)
   },
   id: 'doubleLinePicker'
});
```
<a name="datePicker"></a>

## datePicker(options)
dataPicker 时间选择器，由picker拓展而来，提供年、月、日的选择。

**Kind**: global function  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| options |  |  | 配置项 |
| [options.id] | <code>string</code> | <code>&quot;datePicker&quot;</code> | 作为picker的唯一标识 |
| [options.start] | <code>number</code> | <code>2000</code> | 起始年份 |
| [options.end] | <code>number</code> | <code>2030</code> | 结束年份 |
| [options.onChange] | <code>function</code> |  | 在picker选中的值发生变化的时候回调 |
| [options.onConfirm] | <code>function</code> |  | 在点击"确定"之后的回调。回调返回选中的结果(Array)，数组长度依赖于picker的层级。 |

**Example**  
```js
weui.datePicker({
    start: 2010,
    end: 2016,
    onChange: function(result){
        console.log(result);
    },
    onConfirm: function(result){
        console.log(result);
    },
    id: 'datePicker'
});
```