## 中间件

* ### 定义中间件

    中间件放到 `internal\middleware` 目录下，其定义参考Gin框架的中间件定义即可

* ### 使用中间件

    1. 设置全局中间件

        在 `internal\router\default.go`文件的 `Init`函数中使用`router.SetGlobalMiddleware`方法设置

    2. 设置后端管理路由的中间件

        在 `internal\router\default.go`文件的 `Init`函数中使用`router.SetAdminRoute`方法设置

    3. 设置接口的中间件

        在 `internal\router\default.go`文件的 `Init`函数中使用`router.SetApiRoute`方法设置

    4. 设置单独路由的中间件

        可以在控制器中的 `Routers` 方法中单独设置

        > [!NOTE]
        > api接口单独设置路由
        > 
        > ```go
        > func (con userController) Routes(rg *gin.RouterGroup) {
        >     rg.POST("/info", middleware.JwtAuth(), con.userExample)
        > }
        > ```