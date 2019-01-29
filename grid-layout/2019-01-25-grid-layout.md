### Grid intro
> grid是css的第一个真正的布局系统。和flexbox一样， grid也需要两级DOM层级。container 和items。fr相当于flex-grow。grid-tempalte-columns 和 grid-tempalte-rows指定的是gird里每个row和column的size。grid-gap是先上后下。

### grid-template-columns
>grid-template-columns: 1fr 1fr 1fr;会定义三个等宽的column，还会定义四个vertical 的grid-line.

### flexbox vs grid operations
> 使用flexbox的时候，必须以一些nested 的方式进行flexbox的组合；而使用grid的时候，只需要制定的grid-item必须是gridcontainer的孩子。
1. flexbox是一维的；grid是二维的；
2. flexbox源于内容；grid则是源于layout；flexbox可以隐式的设置item的size，但是grid必须先设置整个的layout。
> grid适合二维的items的对齐；flex适合一维的数据流。通常grid适合页面级的布局而flex适合grid area的某些元素的对齐。 

### grid-column vs grid-row
> grid-column: 1 / 3;实际上要的是1，2列；grid-row：1 / 3；1， 2行。这个属性的功能是将元素进行放置

### grid-template-rows
> grid-template-rows:repeat(4, auto)===grid-template-rows:auto auto auto auto;auto的意思随着content的size。repeat(3, 2fr 1fr) === 2fr 1fr 2fr 1fr 2fr 1fr;

### grid-line 的数字化
> css 里可以根据这个数字化的坐标来定义grid-item的位置


### grid  另外两种语法
> 之前用的是Numbering grid line，还有两种是named grid line 和named grid area，这些选择只是爱好的问题，当然哪种好理解推荐用哪个。在有大量的数字的grid line的时候，可能需要使用named grid line。numbering grid line 和 naming grid line都是需要grid template和grid columns/rows连用的； naming grid area则是通过grid template和grid area来使用的
**每一个named grid area必须形成一个矩形，有些grid track空着也是可以的。**

### Explicit & implicit grid
> 当使用了grid-template-*的属性就是使用了显示的grid;但是 grid items仍然可以放到显示的tracks之外， 这种情况下  隐式的grid item（tracks）可以自动生成，并扩展到可以包含放置的元素。
隐式的tracks默认是auto的。但是grid-auto-columns和grid-auto-rows可以用在container上，来制定所有隐式的tracks的不同size。**隐式的grid tracks不会改变负数grid lines的意义，它仍然开始于显示grid的右下角**

```css
selector {
  grid-auto-rows: 1fr;/*所有隐式的 grid  row是同一个高度*/
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  /*minmax()限制某个值在这个之间；
  auto-fill是要浏览器防止尽可能多的grid tracks。这里的就是同时不违背minmax的设置
  */
  grid-auto-flow: dense;==row dense;
  /*
  默认的算法是grid item 是根据markup里的顺序 一个column挨着一个column ， 行挨着行 放置的，然后wrap；grid-auto-flow是来改变这种放置 算法的。dense则是试图填补grid item之间的gap，可能会改变gird item的顺序
  */
}

```
> auto-fill在没有足够多的item的时候会导致空的grid  tracks。auto-fit则会自动填充可用空间。

### grid item 调整
> 默认每个grid item会被拉伸来填充整个的grid area，但是item的childrren不会被拉伸。，所以grid area会有一个未被使用的height。简单的修复方法就是使用flex。

### image拉伸
> 拉伸图片是有问题的 ，这样会改变宽高比，为了解决这个 问题可以使用object-fit.默认是fill， 充满img 元素，cover和contain 都是保存宽高比，但是cover会去掉某些边缘， contain可能会留有空白。还有就是他改变的是渲染图片的size而不是box的size。

### grid align
> grid module 的alignment除了和flex的一样，还有几个新的属性justify-content/justify-items/justify-self控制的是水平方向的； align-content/align-item/align-self控制的垂直方向上的。

https://gridbyexample.com/examples/example37/










































