
## 命令操作

* ### 运行APP
```shell
PS F:\ginadmin> go run .\cmd\ginadmin\ run -h
Run app

Usage:
  ginadmin run [flags]

Flags:
  -c, --config path string   config path
  -h, --help                 help for run
  -m, --mode string          dev or release (default "dev")
```
* ### 数据表迁移命令
```shell
PS F:\ginadmin> go run .\cmd\ginadmin\ db migrate -h
DB Migrate

Usage:
  ginadmin db migrate [-t table] [flags]

Flags:
  -c, --config path string   config path
  -h, --help                 help for migrate
  -t, --table string         input a table name
```

* ### 数据填充命令

```shell
PS F:\ginadmin> go run .\cmd\ginadmin\ db seed -h   
DB Seed

Usage:
  ginadmin db seed [-t table] [flags]

Flags:
  -c, --config path string   config path
  -h, --help                 help for seed
  -t, --table string         input a table name
```