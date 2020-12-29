# hy-shortview
这是一个Spring Cloud微服务实践项目demo，使用了Eureka注册中心，Spring Config配置中心，Spring Gateway网关等组件，子服务通过openFeign调用，支持负载和服务降级。将操纵Redis和通过Mybatis操纵Mysql功能抽离出来成独立的jar包，并且都支持多数据源配置，子服务按照需要依赖引入并配置数据源。

# 各服务介绍：
### hy-eureka-server 8761 注册中心
服务治理，所有的服务都往这里注册。

### hy-config-server 8888 配置中心
统一管理各服务的配置信息。

### hy-gateway 8080 网关
使用Spring Gateway实现，所有请求的入口，主要负责请求签名验证，调用hy-auth-server来鉴权认证，并将认证的用户信息传递给下游子服务，方便下游子服务获取授权的用户信息。

### hy-auth-server 8001 鉴权子服务
负责用户登陆认证和token校验。

### hy-order-server 8002 订单子服务
一个普通的业务子服务。

### config-test 测试环境配置文件仓库
管理测试环境的各服务配置信息。

### config-prod 生产环境配置文件仓库
管理生产环境的各服务配置信息。

### hy-common 自定义公共jar包
自定义公共jar包，提供统一请求参数和相应参数封装，全局异常捕获，统一参数校验，相关工具类等等。

### hy-data
数据库表对应的映射实体类，统一管理entity。

### hy-starter-redis Redis组件
Redis工具包，支持多数据源。

### hy-starter-mybatis Mybatis组件
Mybatis工具包，支持多数据源。
