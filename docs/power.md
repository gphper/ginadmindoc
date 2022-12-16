## 后台权限

* ### 菜单管理

    后台管理页面的侧导航菜单在 `internal/menu/menu.go` 文件中定义，其中 `Menu`和`Node` 定义的是菜单权限，`NodeSon` 定义的是操作或按钮的权限

    > [!NOTE]
    > 权限是使用 `访问路径+请求方式` 的形式来判断的

* ### 权限管理

    菜单管理设置完之后可以在角色管理中勾选和设置权限<br/>

* ### 模板鉴权

    在模板页面中判断权限，其实主要就是用来判断操作按钮是否需要显示，这时使用 `judgeContainPriv` 函数来判断，格式如下

    ```
    {{if judgeContainPriv $.username 访问路径 请求方式}}
        显示的内容
    {{end}}
    ```
    > [!NOTE|style:flat|label:举例 ]
    > 判断用户是否有用户操作新增文章的权限时
    > ```html
    >    {{if judgeContainPriv $.username "/admin/article/add" "get"}}
    >        <a class="btn btn-primary m-r-5" href="/admin/article/add"> 新增</a>
    >    {{end}}
    > ```

* ### 请求鉴权

    对于url请求的鉴权是在中间件中完成的,具体路径在 `internal\middleware\auth.go` 中的 `AdminUserPrivs` 方法  

## 管理员信息

* ### 获取信息

    在控制器中获取管理员信息时，可以使用 `c.Get()` 的方式获取，默认context中包含以下几个信息
    
    ```go
        // 管理员名称
        c.Set("username", userData.Username)
        // 管理员id
		c.Set("uid", userData.Uid)
        // 管理员角色
		c.Set("groupname", userData.GroupName)
    ```