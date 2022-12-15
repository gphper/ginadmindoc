## 接口文档

* ### 本地安装swag
    
    ```shell
        go install github.com/swaggo/swag/cmd/swag
    ```

* ### 生成文档

    ```shell
        swag init -g cmd/ginadmin/main.go
    ```

* ### 访问接口文档
    > [!NOTE]
    > 只有在debug模式下运行时才能够访问接口文档

    ```
    访问 http://域名:端口/swagger/index.html
    ```
