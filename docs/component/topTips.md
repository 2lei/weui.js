<a name="topTips"></a>

## topTips(content, options)
toptips 顶部报错提示

**Kind**: global function  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| content | <code>string</code> |  | 报错的文字 |
| options | <code>number</code> &#124; <code>function</code> &#124; <code>object</code> |  | 多少毫秒后消失|消失后的回调|配置项 |
| [options.duration] | <code>number</code> | <code>3000</code> | 多少毫秒后消失 |
| [options.callback] | <code>function</code> |  | 消失后的回调 |

**Example**  
```js
weui.topTips('请填写正确的字段');
weui.topTips('请填写正确的字段', 3000);
weui.topTips('请填写正确的字段', function(){ console.log('close') });
weui.topTips('请填写正确的字段', {
    duration: 3000,
    callback: function(){ console.log('close') }
});
```
