## 配置文件

* ### 编写结构体

    在 `configs/config.go` 添加配置项的 struct 类型，例如
    
    ```go
    type AppConf struct {
        BaseConf `yaml:"base"`
    }
    type BaseConf struct {
        Port string `yaml:"port"`
    }
   ```

* ### 在yaml文件中添加配置

    ```yaml
      base:
        port: 20011
    ```

* ### 代码中获取配置信息
    
    ```go
      configs.App.BaseConf.Port
    ```