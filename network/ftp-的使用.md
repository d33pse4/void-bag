# [ftp-的使用](../index/ftp.md#ftp-的使用)


## ftp 语法

```
ftp [options] <host> [port]
ftp xx.xx.xx.xx
```
host 可以是 IP 地址，也可以是 **域名**

## ftp 常用选项

host: 可以是 IP 地址，也可以是域

* -v：显示命令执行过程，相当于 verbose
* -n：不使用自动登录
* -d：详细显示指令执行过程，便于排错货分析程序执行的清醒，相当于 debug
* -i：关闭互动模式，不询问任何问题，相当于 prompt
* -g：禁用通配符（*、?）
* -A：使用匿名进行登录

## # 匿名登录

ftp 允许用户匿名登录，也就是说，不需要密码，只需要在账号的位置输入 anonymous，口令留空，就可以登录，前提是服务器的 ftp 服务配置了允许匿名登录

## # ascii 模式 和 binary 模式有什么区别

ascii 模式：

使用 ascii 模式，传输过程中，会对源文件进行读取，并将文件中的字符格式进行转换，例如：会将 \n (Linux) 转化为 \r\n (Windows)，适用于文本文件，也可以传输二进制文件，但会把二进制文件中匹配的字符进行转换，导致文件损坏

binary 模式：

使用 bin 模式，会将源文件以字节的形式，原封不动的传输，适用于所有文件，但可能文本文件中的换行就没有了，导致没有换行的效果，但现代编辑器非常成熟、强壮，会自动弥补这个问题

## ftp 交互式命令

登录账号，正式进入 ftp 交互后，需要使用 ftp 交互命令，对 ftp 进行操作，例如，上传、下载文件，展示远程目录内容等

远程：

* ls：列出远程服务器上的文件和目录
* cd：更改远程服务器上的目录
* pwd：查看远程计算机目录路径
* delete：删除远程服务器上的文件，示例：`delete <file_name>`
* mdelete：删除远程服务器上的多个文件，示例：`mdelete <file_name>/通配符`
* rename：重命名，示例：`rename <file_name / 目录名>`
* mkdir：在远程服务器创建目录，示例：`mkdir <目录名>`
* rmdir：删除远程服务器上的目录，示例：`rmdir <目录名>`

本地：

* !：临时进入本地模式，用来对本地进行操作
* ? / help：查看交互命令帮助
* !ls / !dir：查看本地计算机目录
* !cd / lpwd / !pwd: Windows 查看本地计算机目录路径
* lcd：更改本地计算机上的目录
* mdir / mls 列出目录信息后写入本地文件或输出到显示器上，示例：`mls <command> <local_file>`，不指定本地文件，用 -，示例：`mls <command> -`

* get / recv：从远程服务器下载文件到本地计算机，示例：`get <file_name>`
* put / send：将本地文件上传到远程服务器，示例：`put <file_name>`
* append：使用本地文件向远程文件中追加文本内容，示例：`mget <local_file> <remote_file>`
* mget：下载多个文件，示例：`mget <file_name>/通配符`
* mput：上传多个文件，示例：`mput <file_name>/通配符`

* open：连接到远程 FTP 服务器，示例：`open <host>`
* close / disconnect：断开连接，但不退出 ftp 程序
* bye 或 quit：断开与 FTP 服务器的连接并退出 ftp 程序
* uesr：在连接后重新以其他用户名登录服务器。

* status：查看当前 FTP 各种设置的状态
* verbose：详细模式开关，默认为：开启详细模式，详细模式会显示所有 FTP 服务器响应的信息
* bell：响铃开关，当一个文件完成传输时，计算机会发出 “嘀” 的响声
* prompt：交互提示开关
* glob：通配符开关，关闭后，mget，mput 中的 * ？ 将不会解释为通配符
* debug：调试开关
* trace：比 debug 更详细
* hash：进度条
* type：查询或设置文件传输模式 ascii 或 binary
* ascii：直接切换 ascii 模式（默认为 ascii 模式）
* binary：直接切换 binary 模式

不常用
remotehelp 
quote

    





#FTP
#文件传输
