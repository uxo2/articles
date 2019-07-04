# 前端异步请求

1、ajax请求

```
var xmlhttp = new XMLHttpRequest()  // 创建异步请求
xmlhttp.onreadystatechange = (req) {  // 设置回调函数
  console.log(req)
}
open(method,url,async)  // 开启连接
xmlhttp.send()  // 发送请求

```

2、promise

promise是一个表示异步操作的最终状态（完成或者失败俩种状态），以及该异步操作的结果值。

new Promise(function(resolve, reject) {
  这里是一个异步操作，操作后判断是否进行resolve还是reject2
}).then(resolve => {
  console.log(resolve) // 上述如果执行resolve的话则进行then
}).catch(err => {
  console.log(err)  /// 执行reject
})

-