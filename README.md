# tp_py_sanic-dev

sanic项目的组件开发分支.python的最低版本要求为3.8

## 组件模板

组件模板可以在没有对应组件时使用`ppm project add --located-path=<located> --kv=source::<默认资源名>`命令添加.只要在服务入口中调用`init(app)`即可注册使用

| 组件名       | 说明                                                 |
| ------------ | ---------------------------------------------------- |
| `decorator`  | handler使用的装饰器组件                              |
| `listener`   | sanic的listenner组件,用于挂载在sanic对象的声明周期中 |
| `middleware` | sanic的自定义中间件组件,用于挂载在handler上"         |
| `rest`       | sanic的RESTful接口组件                               |
| `sse`        | sanic的sse接口组件                                   |
| `ws`         | sanic的websocket接口组件                             |
| `view`       | sanic的动态页面组件                                  |
| `download`   | 下载组件                                             |


## 组件资源模版

组件资源模版是对应组件模版的资源文件/文件夹,当已经添加了组件后要向其中添加额外的资源可以使用`ppm project add --located-path=<located> --kv=source::<资源名>`命令添加.然后再对应的组件模块中的`__init__.py`中导入并在`init(app)`函数中注册即可

| 组件资源名             | 说明                                  |
| ---------------------- | ------------------------------------- |
| `decorator_source`     | handler使用的装饰器文件模版           |
| `listener_source`      | sanic的listenner文件模板              |
| `middleware_reqsource` | sanic的自定义请求中间件文件模版       |
| `middleware_ressource` | sanic的自定义请求中间件文件模版       |
| `rest_source`          | sanic的RESTful接口中资源接口模版      |
| `sse_source`           | sanic的sse接口中资源接口模版          |
| `ws_source`            | sanic的websocket接口中资源接口模版    |
| `view_source`          | sanic的动态页面文件模版               |
| `download_source`      | 下载资源文件模版,多用于实时生成的文件 |
