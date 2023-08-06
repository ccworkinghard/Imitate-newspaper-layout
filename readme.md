这是一个关于CSS布局的小练习。主要是仿照报纸的布局排列。  
遗憾的是，关于多行文本溢出的功能，并没有做到自适应布局，以后学会了再回来优化。
## 一些关键点：
- 标题文字竖向排列：
    ```
    writing-mode: vertical-rl;
    text-orientation: mixed;
    ```

- 整体布局：实现两栏布局
    ```
    父元素：
    display:flex;

    子元素：
    flex: 0 0 x%;
    flex：0 0 x%;
    ```

- 整体布局居中：
    ```
    父元素：
    display:flex;
    flex-direction:colum;
    margin:按需要写

    子元素：
    align-self:center;
    ```

- 多行文本溢出隐藏，用省略号代替（重要）：
    ```
    父元素：
    display:flex;

    子元素：
    /* 盒模型 */
    display: -webkit-box;
    /* 盒内子元素布局方向 */
    -webkit-box-orient: vertical;
    /* 超出隐藏 */
    overflow: hidden;
    /* 文本超出呈现方式：省略号 */
    text-overflow: ellipsis;
    /* 限制文本行数 */
    -webkit-line-clamp: n;
    ```