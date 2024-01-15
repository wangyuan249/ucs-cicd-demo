华为云 CodeArts DevOps 官方演示应用

【现网已公开】凤凰商城示例代码
=========

### 简介

> 【凤凰商城】示例代码套件是一套电子商务商城示例代码。此套示例代码具有结构复杂,逻辑简单,代码量少,技术栈丰富的特点,可以帮助开发者快速学习华为devCloud的各项特性以及使用微服务进行软件开发,测试和部署过程中可能遇到的各种问题。

#### 架构及业务场景

凤凰商城示例程序由5个可以独立开发,测试和部署的微服务组件构成,分别为

* 客户端UI服务:
  * 业务逻辑:用户可以通过浏览器访问此服务的WebUI,并在特定商品上点击Like按钮。服务将用户所选择物品的记录保存在Redis缓存中。
  * 技术栈:Python, Flask框架
  * 应用服务器:Gunicorn
* 管理端UI服务:
  * 业务逻辑:用户可以通过浏览器访问此服务的WebUI,会动态显示客户端UI上用户点击Like按钮的统计数据。此数据来自PostgreSQL数据库。
  * 技术栈:node.js, express框架
  * 应用服务器:server.js
* 工作进程服务:
  * 此服务为后台进程,会监控redis缓存中的物品记录,并将新纪录取出并保存在PostgreSQL数据库中,以便管理端UI可以抽取数据进行统计显示。
  * 技术栈:.net core 或者 java (此服务提供2种技术栈实现了同样的功能,可根据需要修改配置选择其中一个座位运行时进程)  
* Redis缓存
  * 业务逻辑:此服务作为客户端UI服务的数据持久化服务存在。
* PostgreSQL数据库
  * 业务逻辑:此服务作为管理端UI服务的数据源。


#### 应用架构图

![Architecture diagram](./images/architecture.png)

#### 客户端UI

![Architecture diagram](./images/ui01.png)

#### 管理端UI

![Architecture diagram](./images/ui02.png)


