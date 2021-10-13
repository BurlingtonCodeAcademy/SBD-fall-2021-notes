# Flexbox

## Usage 

Flexbox is an amazing tool for website layout and alleviates a lot of the wonkiness that has existed since the beginning of css. You can even nest flexboxes in flexboxes in flexboxes!

Flexbox helps to accomplish the following:
- Horizontal or vertical alignment of elements
- Arrangement (order) of elements
- Space distribution between elements
- Space distribution around elements

Flexbox is one-dimensional can arrange in a row or column, but not both, and is useful for laying out elements such as navigation bars, headers, image galleries, etc.It also fixes CSS layout madness by placing the responsibility for layout with the container, and not asking each item to be responsible for laying itself out


Flexbox works by applying CSS properties to both the container, and the children inside the container:
Add the CSS property `display:flex;` to the container of the items you intend to arrange.
Remember, Flexbox is one dimensional. display:flex arranges your items in a row. This can be changed with `flex-direction: column;`
```
#container {
  display: flex;
  flex-direction: column-reverse;
}
```

## Elements

### Justify-Content
`Justify content` is applied to the flex container as well. It works along the main axis of the flex container.

```
#container {
  display: flex;
  justify-content: center;
}
```
Justifying your content, both horizontally and vertically, with:
- `Flex-start`
- `Flex-end`
- `Center`
- `Space-between`
- `Space-around`

### Align Items
`align-items` is also applied to the flex container. This is similar to justify content, but works along the cross-axis. If your items are arranged in a row, this would act on the vertical axis.
```
#container {
  display: flex;
  align-items: stretch;
}
```
5 Uses:
- `flex-start`
- `flex-end`
- `center`
- `stretch`
- `baseline`

### Flex Direction
Your flex items can be arranged either in a row, or a column. This is done with either `flex-direction:column` and `flex-direction:row`

### Order
Order is a simple property that lets you order items specifically
```
.firstItem {
  display: flex;
  order: 1;
}

.secondItem {
  display: flex;
  order: 2;
}
```

### Align Self
You can also align individual items, rather than all flex items at once. This property accepts the same values as `align-items`, and achieves the same results, but for individual items:
- `flex-start`
- `flex-end`
- `center`
- `stretch`
- `baseline`
```
#container {
  display: flex;
  align-self: flex-start;
}
```