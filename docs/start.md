## 快速开始

* ### git 克隆地址 
   
   ```
   git clone https://github.com/gphper/ginadmin.git
   ```

* ### 下载依赖包
   
   ```go
   go mod download
   ```

* ### 配置 `configs/config.yaml`文件
   
   ```yaml
   mysql:
   -  name: "default"
      username: "root"
      password: "123456"
      database: "db_ginadmin"
      host: "127.0.0.1"
      port: 3306
      max_open_conn: 50
      max_idle_conn: 20
   redis:
      addr: "localhost:6379"
      db: 0
      password: ""
   session:
      session_name: "gosession_id"
   base:
      host: 0.0.0.0
      port: 20011
      log_media: "redis"
   ```

* ### 运行命令 
   `go run .\cmd\ginadmin` <br/>
   访问地址 http://localhost:端口地址/admin/login <br/>
   默认账户：admin  密码：111111

* ### Debug 配置
   + VsCode 配置
   ```launch.json
   {
      "version": "0.2.0",
      "configurations": [
         {
               "name": "ginadmin",
               "type": "go",
               "request": "launch",
               "mode": "debug",
               "program": "${workspaceRoot}/cmd/ginadmin",
               "trace": true,
               "args":[
                  "run",
                  "-c=${workspaceRoot}"
               ],
         }
      ]
   }
   ```

   + Goland 配置
   ![goland配置](https://user-images.githubusercontent.com/18718299/211311066-889e162b-6228-43e4-a5d2-98a00235849b.PNG)