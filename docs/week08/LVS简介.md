# LVS简介

负载均衡的优势：可伸缩性、高可用性、可管理性、价格有效性。

负载均衡的方式：硬件负载均衡，软件负载均衡

LVS的组成部分：最前端的负载均衡层，中间的服务器池层，最后端的数据共享储存层

调度算法：轮询，加权轮询，最少连接，加权最少连接，基于局部性的最少连接，带复制的基于局部性最少连接，目标地址散列，源地址散列

LVS是基于IP负载均衡的计数，通过IPVS模块实现，位于负载调度器上。

负载均衡技术分类：

- 通过`NAT`实现虚拟服务器（`VS/NAT`）
- 通过直接路由实现虚拟服务器（`VS/DR`）
- 通过IP隧道实现虚拟服务器（`VS/TUN`）

`VS/NAT`：内网集群，支持端口映射；所有进出报文都经过负载均衡器，调度器易成为性能瓶颈

`VS/DR`：内网集群，不支持端口映射，响应报文直接返回给客户端，负载均衡器仅负责处理入站请求

`VS/TUN`：公网集群，不支持端口映射，响应报文直接返回给客户端，负载均衡器仅负责处理入站请求
