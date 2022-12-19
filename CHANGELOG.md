# cp-0.0.1

提供了基本的组件

## 新增组件模板

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

## 新增组件资源模版

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

## 新增基础组件

| 组件名       | 说明                                                                                |
| ------------ | ----------------------------------------------------------------------------------- |
| `main`       | sanic项目的入口模块组件                                                             |
| `dockerfile` | sanic项目的dockerfile组件文件                                                       |
| `servapi`    | 包含RESTful接口,sse接口,和websocket接口的服务模版                                   |
| `servmvc`    | 由jinja2模版动态渲染的应用模版                                                      |
| `servmvpapi` | 由jinja2模版动态渲染的应用模版同时包含RESTful接口,sse接口,和websocket接口的服务模版 |
| `servrest`   | RESTfulapi服务模版                                                                  |
| `servspa`    | 混合RESTful,ws,sse和download的单页应用模版                                          |
| `servstatic` | 静态资源服务模板                                                                    |
| `servws`     | websocket服务模版                                                                   |