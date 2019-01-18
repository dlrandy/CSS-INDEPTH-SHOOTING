### absolute unit
> Pixels, Points, picas,mm, cm, in <br/>
1in = 25.4mm = 2.54cm = 6pc = 72pt = 96px
### relative unit
> 相对的单位实际上是css，用来处理resonsive的一个工具。
### em rem
> 大多数浏览器默认的字体大小是16px。em用在font-size上的时候，是相对于inherit的，其他属性的时候则是相对于自身字体的大小的。注意em nest的情况。:root等价于html。
### 单位选择的最佳实践
> 一般在单位选择上有疑惑的时候， rem 用于字体， px用于border， em用于其他属性，对于容器之类的使用%, vw.
### css里的反模式
> 把html的font-szie重置为为10px，然后使用rem。因为这样要写很多的style，因为10px太小了，每个元素你都要进行设置。同时这也是以px进行思考的。**不要以像素来思考css**。因该习惯模糊值。(_need_check_again_)
### 最佳实践
>  在项目一开始的时候，就要设置好base font (几组通用的size)
### Viewport units
> viewport指的是页面的空白区域 
### Unitless
> 支持的属性有line-height,z-index, font-weight, length-unit(px, em, rem, %)
### Custom property(css vairables)
> 同名变量, 特指性越高的变量优先级越高。scoped 变量。
```javascript
      let rootEle = document.documentElement;
      let styles = getComputedStyle(rootEle);
      let mainColor = styles.getPropertyValue("--main-bg");

      console.log(String(mainColor).trim());

      setTimeout(() => {
        rootEle.style.setProperty("--main-bg", "#cdf");
      }, 3000);
```











