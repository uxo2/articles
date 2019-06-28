# CSS知识总结

### 1.1 左边定宽，右边自适应方案：
- float + margin-left
- float + calc(100%-width)

### 1.2 左右两边定宽，中间自适应：
- float + margin
- float + calc
- flex
- 圣杯布局（设置BFC，margin负值法)

### 1.3 左右居中

- 行内元素 +  `text-align: center`
- 定宽块状元素: 左右 `margin` 值为 `auto`
- 不定宽块状元素: `table`布局，`position + transform`


### 1.4 上下垂直居中

- 定高 + `margin`，`position + margin`(负值)
- 不定高 
    - `position` + `transform`
    - `flex`
    - `IFC + vertical-align:middle`
```
/* 设置 inline-block 则会在外层产生 IFC，高度设为 100% 撑开 wrap 的高度 */
.wrap::before {
  content: '';
  height: 100%;
  display: inline-block;
  vertical-align: middle;
}
.wrap {
  text-align: center;
}
.center {
  display: inline-block;  
  vertical-align: middle;
}
```

### 1.5 盒模型：content（元素内容） + padding（内边距） + border（边框） + margin（外边距）

> 延伸： `box-sizing`

- `content-box`：默认值，总宽度 = `margin` + `border` + `padding` + `width`
- `border-box`：盒子宽度包含 `padding` 和 `border`，`总宽度 = margin + width`
- `inherit`：从父元素继承 `box-sizing` 属性

### 1.6 BFC、IFC、GFC、FFC：FC（Formatting Contexts），格式化上下文

> `BFC`：块级格式化上下文，容器里面的子元素不会在布局上影响到外面的元素，反之也是如此(按照这个理念来想，只要脱离文档流，肯定就能产生 `BFC`)。产生 `BFC` 方式如下

- `float` 的值不为 `none`。
- `overflow` 的值不为 `visible`。
- `position` 的值不为 `relative` 和 `static`。
- `display` 的值为 `table-cell`, `table-caption`, `inline-block`中的任何一个
