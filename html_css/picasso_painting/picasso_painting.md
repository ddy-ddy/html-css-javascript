## Purpose

In this course, you'll learn how to use some intermediate CSS techniques by coding your own Picasso painting webpage. You'll learn about **SVG icons**, **CSS positioning**, and review other CSS skills you've learned.



## Effect



## Knowledge

#### 1. 元素重叠 - `z-index`

- 详见https://developer.mozilla.org/zh-CN/docs/Web/CSS/z-index

- `z-index`指定盒子在当前堆叠上下文中的堆叠层级

```css
#back-wall {
  position: absolute;
  z-index: -1;
}
```

#### 2. 元素在文档中的定位方式 - `position`

- 详见https://developer.mozilla.org/zh-CN/docs/Web/CSS/position
- static: 正常的布局行为
- fixed: 固定的布局行为。如页面上下滑动时，该布局元素不动
- relative: 原有位置所占空间不变，现位置相对原位置偏移

- absolute: 原有位置空间被移除，通过与最近的非static定位偏移参数来决定自己的位置

- sticky: 某个阈值前是相对定位，阈值后事固定定位。如页面滑动一段举例后，顶部固定



## Code

- index.html

```html

```

- styles.css

```css

```

