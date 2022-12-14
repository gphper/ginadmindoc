
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

* ### 创建Controller文件
> go run .\cmd\ginadmin\ file controller -p=shop -c=shopController -t=admin
```shell
  PS F:\ginadmin> go run .\cmd\ginadmin\ file controller -h
  create controller file

  Usage:
    ginadmin file controller [-p pagename -c controllerName -m methods] [flags]

  Flags:
    -c, --controllerName string   input controller name eg: AdminController
    -h, --help                    help for controller
    -m, --methods string          input methods eg: index:get,add:get (default "list:get,add:get,save:post,edit:get,del:get")
    -p, --pagename string         input pagename eg: setting
    -t, --typename string         input typename api or admin
```

* ### 创建Model文件
> go run .\cmd\ginadmin\ file model -m shop_type
```shell
  PS F:\ginadmin> go run .\cmd\ginadmin\ file model -h
  create model

  Usage:
    ginadmin file model [-m modelName] [flags]

  Flags:
    -h, --help           help for model
    -m, --model string   input model name eg: shop_items 
```