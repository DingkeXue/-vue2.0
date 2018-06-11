 

vue 作为mvvm

组建化框架, 有vuex vue-router 再结合webpack形成一个整体的前端解决方案.

### 数据状态和视图的映射关系

* mvvm相对于mvc,  它们核心思想都是数据驱动视图, mvvm在数据变化后自动更新视图, 而mvc虽然分层, 但还是要手动维护数据和视图的关系, 在数据状态复杂的情况下, 一个数据变化后可能引起多处视图的变化, 一次操作也可能有多个数据变化;

* 手动更新DOM不管是用jQuery 还是 mvc的backbone,都会显得繁琐, 数据状态越复杂, 维护dom的成本就越高, 出错的可能性也变大; 

* 利用虚拟dom来diff自动更新页面, 大大减少了更新视图的复杂性, 为控制绑定的粒度, vue中是一个组件作为一个watcher, 因为粒度太细, 会有依赖追踪的性能消耗.

### 组件化

* 组件化从传统的功能组件到页面UI组件的转化, 使页面的粒度更细, 更易于组合, 来应付各种新需求的变化, jQuery时代一般功能性的东西才会封装成组件, 比如日历, 下拉框, 验证组件; 
* UI层面的组件化之后, 头部 尾部 每一行的item 都可以作为一个组件, 因为这些UI可能多个页面都使用到, 结构样式类似, 如果内容不一样, 可以用props传入 ,  如果后续需求有变化, 样式或者结构需要改变, 只需要改动item一个地方.  

* jQuery使用插件 一般在页面定义一个div, 利用id获取元素后, 实例化插件, Vue中使用声明式的组件使用方式 , 页面结构更清晰, 可以相互嵌套 显得更灵活

`  <app>
        <app-header></app-header>
        <app-content></app-content>
        <app-footer></app-footer>
    </app>`
    
### vue-router
vue-router 可以由前端自定义各种复杂的路由, 子路由也能产生历史记录, 用户回退的时候可以减少页面渲染的区域 只渲染框架的子页面; 另外所有的html, 可以缓存 , 有利于提高性能, 适合移动应用.

### vuex
* vuex 把应用状态保存在一个地方, 引用vue作者的话说, 可以随时保存应用快照, 实现 time-travel, 比如说用户登录后一键返回到上次浏览的状态 , 开了哪些tab,浏览到第几页等等 另外如果程序出现bug, 也可以通过vuex还原用户当前状态, (比如程序出现异常的时候, 把vuex上传到日志 );

* 另外有利于做debug.vuex也使数据流更清晰, 因为改变数据都要通过vuex的action, 只要在这里断点, 就知道改变数据的源头在什么地方, 数据变化变得可追踪.





