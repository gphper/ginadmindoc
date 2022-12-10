## 1. git 克隆地址 
   
   ```
   git clone https://github.com/gphper/ginadmin.git
   ```

## 2. 下载依赖包
   
   ```go
   go mod download
   ```

## 3. 配置 `configs/config.yaml`文件
   
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

## 运行命令 
   `go run .\cmd\ginadmin` <br/>
   访问地址 http://localhost:端口地址/admin/login <br/>
   默认账户：admin  密码：111111
