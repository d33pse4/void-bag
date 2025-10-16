# [frp-的-http-示例](../index/frp.md#frp-的-http-示例)

## # 通信流程

启动 frps 后，公网服务器开始监听 7000 端口
启动 frpc 后，内网计算机使用一个随机端口(port 1)，访问公网服务器的 7000 端口
双方经过协商后，建立 **控制链路**（7000 <=> port 1），用于传输 **控制数据**
同时，内网计算机通过 port 1 向 服务器 7000 发送请求，请求服务器监听 2233 端口
服务器开始监听 2233 端口
此时，用户请求 2233 

## # 部署流程

### # 我使用的是阿里云 ECS

我使用的是阿里云 ECS

### # 准备一台内网计算机

我使用的是 RaspberryPi

### # 访问 [frp 的 GitHub](https://github.com/fatedier/frp/)，下载 C / S 端对应的应用程序

我下载的是：

外网服务器需要用：frp_0.65.0_linux_amd64.tar.gz

内网计算机需要用：frp_0.65.0_linux_arm64.tar.gz


### # 将下载的 frps、frps.toml 传输到云服务器(自定义传输的目标位置)

我直接传输到 /home/username 目录上了

### # 修改 frps.toml 配置文件

```
# frp 服务绑定的端口，提供给内网计算机访问
bindPort = 7000

vhostHTTPPort = 2233
```

### # 将下载的  frpc、frpc.toml 在内网计算机上(自定义传输的目标位置)

我直接传输到我的 /home/username 目录上了

### # 修改 frpc.toml 配置文件

```
# 外网服务器 IP
serverAddr = "x.x.x.x"
# 外网服务器 Port，内网计算机访问外网服务器的端口
serverPort = 7000

[[proxies]]
name = "web"
type = "http"
localPort = 80
customDomains = ["www.yourdomain.com"]
```

### # 在云服务器中，放行 frp 工作时所需要的端口

通过阿里云安全组策略放行 7000、6000 端口

### # 服务器端运行命令

```
sudo ./frps -c frps.toml
```

### # 客户端运行命令

```
sudo ./frpc -c frpc.toml
```

### # 确保内网计算机已运行 http 服务，并尝试通过浏览器访问内网计算机 http 服务

```
http://xx.xx.xx.xx:2233
```


## # 标签

#内网穿透 #FRP

## # 参考链接

[FRP 官方文档](https://gofrp.org/zh-cn/docs/examples/vhost-http/)

## # 反链