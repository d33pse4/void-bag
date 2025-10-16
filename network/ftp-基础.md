# # [ftp-基础](../index/ftp.md#ftp-基础)

## # ftp-是什么

FTP 全称 File Transfer Protocol，中文名字，文件传输协议，简称 FTP

一个用于在网络上的不同计算机之间传输文件的协议，一台作为服务器，另一台作为客户端，就可以实现文件的上传、下载

## # ftp-是基于-tcp-还是-udp-的


FTP 是一种基于 TCP 的协议，采用 C / S 模式，不支持 UDP 的协议

## # ftp-的客户端软件有哪些

Windows：Filezilla、WinSCP 等

Linux：ftp 等

## # ftp-的服务端软件有哪些

Linux：vsftpd、ProFTPD、wu-ftpd、lukemftpd，其中 vsftpd 为大部分 Linux 发行版默认安装的软件，应用最广

## # ftp-怎么安装

以 Linux 为例：

服务端：`sudo apt install vsftpd`

客户端：`sudo apt install ftp`

## # ftp-所使用的端口

20 端口：用于传输文件

21 端口：用于传输控制命令

## # 标签

#FTP #文件传输



## # 反链



















