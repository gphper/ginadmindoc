## 定时任务

* ### 添加任务
    在 `pkg/cron/cron.go`  添加定时执行任务

    > [!NOTE]
    > 使用的 `github.com/robfig/cron` 第三方库，具体可参考官方文档

* ### 启动定时任务
    运行程序时默认开启定时任务
    关闭定时任务时使用 `-t=close` 进行关闭<br/>
    参考命令 [run cli](/cli.md#运行APP)
    > [!NOTE]
    > -t 用来应对同一项目部署在多个服务器时使用