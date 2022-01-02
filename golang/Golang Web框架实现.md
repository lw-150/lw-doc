# WEB框架实现
## WEB框架核心能力
* 路由(Routing)：将请求映射到函数，支持动态路由。例如'/hello/:name。
* 模板(Templates)：使用内置模板引擎提供模板渲染机制。
* 工具集(Utilites)：提供对 cookies，headers 等处理机制。
* 插件(Plugin)：Bottle本身功能有限，但提供了插件机制。可以选择安装到全局，也可以只针对某几个路由生效
