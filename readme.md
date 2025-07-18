做一下 html css js 小练习

### 0618 drank-water:

small 标签，用来将文本显示为比周围文字更小的字号

![1750214573940](image/readme/1750214573940.png)

在 `:root` 中定义的变量是全局变量，可在整个文档的任何 CSS 选择器中引用。

flex-wrap 用于控制 flex 容器内子元素如何换行

align-items: center; 在 flex 或 grid 布局中，控制子元素在交叉轴方向上的对齐方式

justify-content:center；在 flex 或 grid 布局中，控制子元素在主轴方向上的对齐方式

text-align：center; 控制块级元素内的**文本内容**或 **行内元素** （如 `<img>`、`<a>`）的水平对齐方式。

![1750218577014](image/readme/1750218577014.png)

`transition: 0.3s ease;` 是 CSS 中用于实现平滑动画效果的属性，它允许元素的属性值在一定时间内从一个状态过渡到另一个状态。

### 0619 drawing-app

`display: inline-flex;` 是 CSS 中一种混合显示模式，结合了 **内联元素（inline）** 和 **弹性容器（flex）** 的特性。

![1750342360633](image/readme/1750342360633.png)

- **`1rem`** ：这里的 `rem` 是相对于根元素（也就是 `<html>` 元素）字体大小的单位。假设根元素的字体大小是默认的 `16px`，那么 `1rem` 就相当于 `16px`。

`margin-left: auto;`将元素的左侧外边距自动扩展，从而使元素在其父容器中实现特定的对齐效果。具体表现如下：

1. **水平居右** ：当与 `margin-right: 0;` 配合使用时，元素会被推至父容器的右侧。
2. **均分空间** ：如果同时设置 `margin-right: auto;`，元素会在父容器中水平居中（左右外边距平均分配剩余空间）。
3. **块级元素独占一行** ：对于行内元素或行内块元素，设置 `display: block;` 后，结合 `margin-left: auto;` 可使其独占一行并居右。
4. `ctx.beginPath()` - 开始一个新的路径
5. `ctx.moveTo(x1, y1)` - 将画笔移动到起点
6. `ctx.lineTo(x2, y2)` - 从起点绘制一条直线到终点
7. 设置线条样式：

   - `ctx.strokeStyle = color` - 线条颜色（这里的 `color`应该是函数外部定义的变量）
   - `ctx.lineWidth = size * 2` - 线条宽度（`size`也应该是外部变量）

8. `ctx.stroke()` - 实际绘制线条

### 0622 notes-app

`localStorage`是浏览器里的一种存储机制，它以键值对的形式将数据永久存储在浏览器中，除非手动删除。

因为 `localStorage`中存储的只能是字符串，所以在存储对象时，通常会先用 `JSON.stringify()`将对象转换为字符串。

`marked(value)` 是在调用 **Marked.js** 库，它的作用是将 **Markdown 格式的文本**转换为 **HTML 代码** 。

`outline: none;` 是 CSS 中用于移除元素获得焦点时默认显示的轮廓线（outline）的属性

### 0623 good cheap fast

- `id="cheap"`：为元素分配唯一标识符，用于与 `<label>`关联。
- `class="toggle"`：用于 CSS 选择器匹配，添加自定义样式。

**关联机制**

`for="cheap"`：将标签与 `id="cheap"`的输入框绑定。
→ **点击标签时，会自动触发关联复选框的状态切换** 。

### 0624 drag-n-drop

JavaScript 是通过 **DOM API** 来操作 HTML 元素的，所以不需要在 HTML 中直接添加 `on` 事件属性（例如 `<div ondragstart="..." />`）。

- **事件绑定** ：通过 `addEventListener`，JavaScript 代码为 `body` 和 `.empty` 元素绑定了事件监听器，响应用户的拖拽操作。
- **事件冒泡** ：拖拽相关的事件（如 `dragstart` 和 `dragend`）被绑定到 `body` 上，借助事件冒泡机制触发这些事件。
- **HTML 中没有事件处理器** ：HTML 中没有显式的 `on` 事件处理器，所有的事件绑定和处理都是通过 JavaScript 完成的。
- **`dragstart`** ：当拖动 `fill` 元素时，会触发 `dragstart` 事件。在 `dragStart` 函数中，如果目标元素包含 `fill` 类（即我们拖拽的元素），它会添加 `hold` 类并使其不可见，准备开始拖拽。
- **`dragend`** ：拖拽结束后，`dragEnd` 会被触发，这时会恢复元素的类名为 `fill`，表示拖拽结束。
- **`dragover`, `dragenter`, `dragleave`, `drop`** ：这些事件是在 `.empty` 元素上触发的，目的是控制拖拽过程中的行为：
- `dragover`：允许元素被拖拽到该区域。
- `dragenter`：当拖拽元素进入目标区域时，修改目标区域的样式。
- `dragleave`：当拖拽元素离开目标区域时，恢复目标区域样式。
- `drop`：当元素被拖放到目标区域时，将 `fill` 元素插入到目标区域。

  `setTimeout` 的作用是确保 `invisible` 类的添加在浏览器的下一次渲染中生效，通常用于实现动画或延迟效果。

  ## 0628 hoverboard

  element.style.boxShadow = ` ``0 0 3px ${color}, 0 0 10px ${color}` `;

使用了 ES6 的模板字符串（template literals）来动态设置元素的阴影效果，允许多个阴影叠加，创建更复杂的视觉效果。

1. 第一层是模糊半径为 3px 的基础阴影
2. 第二层是模糊半径为 10px 的扩散阴影
3. 两层阴影都使用同一个变量 `color` 作为颜色值
