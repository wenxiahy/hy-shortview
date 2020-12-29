# hy-shortview
这是一个Spring Cloud微服务实践项目demo，使用了Eureka注册中心，Spring Config配置中心，Spring Gateway网关等组件，子服务通过openFeign调用，支持负载和服务降级。将操纵Redis和通过Mybatis操纵Mysql功能抽离出来成独立的jar包，并且都支持多数据源配置，子服务按照需要依赖引入并配置数据源。

# 各服务介绍：
hy-eureka-server 8761 注册中心<br/>
hy-config-server 8888 配置中心<br/>
hy-gateway 8080 网关<br/>
hy-auth-server 8001 鉴权子服务<br/>
hy-order-server 8002 订单子服务<br/>
config-test 测试环境配置文件仓库<br/>
config-prod 生产环境配置文件仓库<br/>
hy-common 自定义公共jar包<br/>
hy-starter-redis Redis组件<br/>
hy-starter-mybatis Mybatis组件<br/>
