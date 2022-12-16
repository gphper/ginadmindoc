
## 定义错误类型 <br/>
* ### 只返回错误信息时
>  package `github.com/gphper/ginadmin/internal/errorx`

	```go
		err = apicon.FormBind(c, &req)
		if err != nil {

			apicon.Error(c, errorx.NewCustomError(errorx.HTTP_BIND_PARAMS_ERR, "绑定参数出错"))
			return
		}
	```

* ### 需要将err信息一起打印或记录时
>   package `github.com/gphper/ginadmin/internal/errorx`
```go
    err = db.Count(&count).Error
	if err != nil {
		
		return pd, errorx.NewCustomErrorWrap(errorx.MYSQL_COUNT_ERR, "page oprion error", err)
	}
```

## 控制器中使用 <br/>

* ### 在后台管理页面展示错误 `con.ErrorHtml(c *gin.Context, err error)`
```go
    articleData, err := paginater.PageOperation(c, adminDb, 1, &articleList)
	if err != nil {
		con.ErrorHtml(c, err)
		return
	}
```

* ### 在接口中展示错误 `apicon.Error(c *gin.Context, err error)`
```go
    err = apiservice.NewApiUserService().Register(req)
	if err != nil {
		apicon.Error(c, err)
		return
	}
```
