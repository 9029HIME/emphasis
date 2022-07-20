# 1-SOA、分布式、微服务的区别

分布式是一个基础概念，主旨是将不同的系统分开部署在不同的机器上，从而提高系统整体的可用性，SOA和微服务都是分布式架构。

SOA更像是一个【只有注册中心】的微服务架构。

微服务的分布式更加的彻底和全面，并且还有许多服务中间件，比如网关、远程调用、分布式事务等。

# 2-微服务怎么拆

还是那句经典原则高内聚低耦合，职责单一，但是服务粒度不要太细。总体上是基于业务方向拆分的，比如授信、借款、还款，账户等。并且最初的拆分不要太细，可以随业务演进逐步细分。

# 3-Nacos为什么要用客户端拉的方式同步配置

主要是为了减少Nacos的压力，如果采用推的方式，虽然实时性有了保证，但Nacos需要为每个客户端都维持一个心跳需要消耗挺多资源，而配置很多时候不需要频繁更改，实时性要求比较低，所以采用客户端拉的方式会比较好。

# 4-网关的作用

可以处理和业务无关的全局处理，它作为【微服务】的网关，用来路由这个请求被Nginx转发后，第一个要到达的微服务。如果说Nginx是前端到后端的网关，那么微服务则是Nginx到微服务的网关。

# 5-熔断和降级

具体看TODO

熔断：命中熔断策略后，直接与下游断了联系

降级：熔断开启后的兜底处理

# 6-Seata的实现原理

TODO，整理之前的笔记

主要讲AT 