# store-spec


## inited 机制 

```js
// store
{
    sender: {
        inited: false,
        items: []
    }
}
```

```js
// 加载列表时
if (!store.sender.inited) {
    getSender({
        success: function (data) {
            store.sender.items = data
        }
    })
}
```

```js
addSender({
    // 新增时
    success: function (data) {
        // 已初始化再添加
        if (store.sender.inited) {
            store.sender.items.push(data)
        }
    }
})
```
