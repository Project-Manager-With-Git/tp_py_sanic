# tp_py_sanic

sanic项目的模板

python构造服务在性能方面不占优势,唯一可以想到的原因有如下:

1. 希望使用其计算库,python是多数计算库的接口语言,比如pytorch,pandas等这是别的语言没有的优势.
2. 对并发性能要求不高,但要求快速开发快速迭代.这种需求一般用在工具型应用上,用啥不重要因为用户基本不会太多(最多万级),且对体验有一定容忍度.很少有像python这样可以半天弄出个能跑的服务的编程语言.

sanic是python环境下最成熟的异步语法微框架之一,不过异步语法框架的优势仅在io性能上,开发会比同步语法的略难受些,但还是可以进行快速开发快速迭代的.至于计算库,它们会造成异步语法框架堵塞,因此一般要放入进程池或者线程池中执行,因此会增加复杂性性能还反而变低了.

这个模版比较适合的使用场景是给只会python的人用来创建io密集型web服务

## 项目组织形式

本项目是sanic项目的模板,使用分支管理组件和模版的开发,tag固定版本,

+ dev分支:维护最新的的组件,组件tag全部从这里分出,统一使用cp-0.0.0作为前缀
+ master分支用于测试各种模版配置,模版tag全部从这里分出,统一使用api-0.0.0这样的形式,前缀分为:
    + `static`,单纯的静态资源服务模板
    + `rest`,单纯的RESTfulapi服务模版
    + `ws`,单纯的websocket服务模版
    + `api`,包含restful接口,sse接口,和websocket接口的服务模版
    + `spa`,混合api,ws,sse和download的单页应用模版.
    + `mvc`,由jinja2模版动态渲染的应用模版
    + `mvcapi`,由jinja2模版动态渲染的应用模版同时包含restful接口,sse接口,和websocket接口的服务模版

## 用法说明

使用模版构造项目后可以进行如下进一步操作:

+ 增加调试用的客户端组件

    + `ppm project add cp_py_files@v0.0.2//aiossecli --located-path=aiossecli.py` 异步sse客户端
    + `ppm project add cp_py_files@v0.0.2//ssecli --located-path=ssecli.py` 同步sse客户端
    + `ppm project add cp_py_files@v0.0.2//aiowscli --located-path=aiowscli.py` 异步websocket客户端
    + `ppm project add cp_py_files@v0.0.2//wscli --located-path=wscli.py` 同步websocket客户端

+ 增加功能组件中的资源项

    + `ppm project add tp_py_sanic@cp-0.0.1//rest_source --located-path=testsanic/rest/usernamespace --kv=source::user`增加一个api资源
    + `ppm project add tp_py_sanic@cp-0.0.1//ws_source --located-path=testsanic/ws/usernamespace.py --kv=source::user`增加一个websocket资源
    + `ppm project add tp_py_sanic@cp-0.0.1//sse_source --located-path=testsanic/sse/usernamespace.py --kv=source::user`增加一个sse资源

+ 如果使用单页应用,参数中设置`spa`为`true`