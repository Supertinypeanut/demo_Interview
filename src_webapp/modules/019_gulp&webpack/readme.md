# gulp

* 流处理：Gulp是一个基于流的构建系统
* 没有产生中间文件：使用Gulp的优势就是利用流的方式进行文件的处理，通过管道将多个任务和操作连接起来，因此只有一次I/O的过程，流程更清晰，更纯粹。
* Gulp去除了中间文件，只将最后的输出写入磁盘，整个过程因此变得更快。

* 常用插件：
```
gulp-autoprefixer:css前缀
gulp-cssnano：压缩
gulp-less：less

gulp-uglify：压缩JS
gulp-babel：语法转换
```

# webpack

* 打包原理：所有的依赖被打包为一个JS文件，通过代码分割成单元片段并按需加载。
* 引入： 以 commonJS 的形式来书写脚本，但对 AMD/CMD 的支持也很全面，
* 所有静态资源模块化；
* 扩展性强，插件机制完善

* 【loader】用于加载某些资源文件。因为webpack本身只能打包common.js规范的js文件，对于其他资源如css，img等，是没有办法加载的，这时就需要对应的loader将资源转化，从而进行加载。
* 【plugin】用于扩展webpack的功能。不同于loader，plugin的功能更加丰富，比如压缩打包，优化，不只局限于资源的加载。
* css-loader: 加载.css文件
* style-loader:使用`<style>`将css-loader内部样式注入到我们的HTML页面

# 区别

* webpack是一个模块打包器，强调的是一个前端模块化方案，更侧重模块打包，我们可以把开发中的所有资源都看成是模块，通过loader和plugin对资源进行处理。
* gulp是一个前端自动化构建工具，强调的是前端开发的工作流程，可以通过配置一系列的task，第一task处理的事情（如代码压缩，合并，编译以及浏览器实时更新等）。然后定义这些执行顺序，来让glup执行这些task，从而构建项目的整个开发流程。自动化构建工具并不能把所有的模块打包到一起，也不能构建不同模块之间的依赖关系。