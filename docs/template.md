## 模板渲染

* ### 书写模板
    所有的后台模板都写到 `web/views/template` 目录下面，并且分目录存储，调用时按照 `目录/模板名称` 的方式调用

    > [!NOTE|style:flat|label:举例 ]
    > `web/views/template/article/article_list.html` 模板文件，控制器中调用时使用如下代码
    > ```
    >    con.Html(c, http.StatusOK, "article/article_list.html", gin.H{
    >        "articleData": articleData,
    >        "created_at":  c.Query("created_at"),
    >        "title":       c.Query("title"),
    >    })
    > ```

* ### 自定义方法
    有时需要自定义一些再模板中直接使用的函数，这时可以在 `pkg\template\default.go` 文件中的进行定义，使用方法参考已有模板函数的使用，或者查阅golang官方模板文档

* ### 模板分页

    1. 控制器查询操作

        控制器中调用 `pkg\paginater\paginater.go`文件中的 `PageOperation`方法
        ```go
        articleData, err := paginater.PageOperation(c, adminDb, 1, &articleList)
        if err != nil {
            con.ErrorHtml(c, err)
            return
        }
        ```

    2. 模板展示

        ```html
        {{ .articleData.PageHtml }}
        ```    