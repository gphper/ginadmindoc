## 控制器操作

* ### 后端控制器
1. 后端控制器集成 `internal/controllers/admin下的BaseController`
2. 后台控制器要实现 `internal/router/icontroller 下的 IAdminController`

* ### 接口控制器
1. 接口控制器集成 `internal/controllers/admin下的BaseController`
2. 接口控制器要实现 `internal/router/icontroller 下的 IApiController`

* ### 使用命令创建控制器
参看 [cli](/cli.md#创建Controller文件)