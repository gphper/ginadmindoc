## 数据库操作

* ### models下定义的文件均需要实现 `internal\models\default.go`文件中的`GaTabler`接口，并将实现该接口的指针写入到 `GetModels` 方法中
   
   ```go
   func GetModels() []interface{} {
       return []interface{}{
           &AdminUsers{},
           &AdminGroup{},
       }
   }
   ```

* ### 配置文件中配置多数据库连接
    1. 配置yaml文件
    ```yaml
    mysql:
    - name: "default"
        username: "root"
        password: "123456"
        database: "db_beego"
        host: "127.0.0.1"
        port: 3306
        max_open_conn: 50
        max_idle_conn: 20
    - name: "pw"
        username: "root"
        password: "123456"
        database: "db_beego"
        host: "127.0.0.1"
        port: 3306
        max_open_conn: 50
        max_idle_conn: 20
    ```
    2. 在model文件 `GetConnName` 方法中设置连接名称
    ```golang
    func (au *AdminUsers) GetConnName() string {
        return "default"
    }
    ```
* ### 使用命令生成 Model 文件和相应的 Dao 文件
参考 [file cli](/cli.md#创建Model文件)