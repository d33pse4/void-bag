# [ftp-的使用](../index/ftp.md#ftp-的使用)

## ftp 语法

```
ftp [options] <host/domain> [port]
```

## ftp 常用选项

* -n：不使用自动登录，**之后不知道该怎么使用，登陆，切换 pasv 模式后，无法执行 ls**
* -v：显示命令执行过程，等价于交互命令中的 `verbose`
* -d：详细显示指令执行过程，便于排错货分析程序执行的清醒，，等价于交互命令中的 `debug`
* -i：关闭互动模式，不询问任何问题，等价于交互命令中的 `prompt`
* -g：禁用通配符（*、?），等价于交互命令中的 `glob`
* -A：匿名登录

## # 匿名登录

ftp 允许用户匿名登录，也就是说，不需要密码，只需要在账号的位置输入 anonymous，口令留空，就可以登录，前提是服务器允许匿名登录

匿名用户登录后所在目录：`/srv/ftp`

启用匿名登录，需要修改[配置文件](vsftpd-配置文件详解.md)

## # ascii 模式 和 binary 模式有什么区别

ascii 模式：

使用 ascii 模式，传输过程中，会对源文件进行读取，并将文件中的字符格式进行转换，例如：会将的 **Linux** 的 **\n** 转化为 **Windows** 的 **\r\n**，适用于文本文件，也可以传输二进制文件，但会把二进制文件中匹配的字符进行转换，导致文件损坏

binary 模式：

使用 bin 模式，会将源文件以字节的形式，原封不动的传输，适用于所有文件，但可能文本文件中的换行就没有了，导致没有换行的效果，但现代编辑器非常成熟、强壮，会自动弥补这个问题

优先使用 binary 模式

## ftp 交互式命令

登录账号，正式进入 ftp 交互后，需要使用 ftp 交互命令，对 ftp 进行操作，例如，上传、下载文件，展示远程目录内容等


* ls：列出远程服务器上的文件和目录
* cd：更改远程服务器上的目录
* pwd：查看远程计算机目录路径
* delete：删除远程服务器上的文件，示例：`delete <file_name>`
* mdelete：删除远程服务器上的多个文件，示例：`mdelete <file_name>/通配符`
* rename：重命名，示例：`rename <file_name / 目录名>`
* mkdir：在远程服务器创建目录，示例：`mkdir <目录名>`
* rmdir：删除远程服务器上的目录，示例：`rmdir <目录名>`
* !：临时进入本地模式，用来对本地进行操作
* ? / help：查看交互命令帮助
* !ls / !dir：查看本地计算机目录
* !cd / lpwd / !pwd: Windows 查看本地计算机目录路径
* lcd：更改本地计算机上的目录
* mdir / mls 列出目录信息后写入本地文件或输出到显示器上，示例：`mls <command> <local_file>`，不指定本地文件，用 -，示例：`mls <command> -`

* get / recv：从远程服务器下载文件到本地计算机，示例：`get <file_name>`
* put / send：将本地文件上传到远程服务器，示例：`put <file_name>`
* append：使用本地文件内容追加到远程文件末尾，示例：`mget <local_file> <remote_file>`
* mget：下载多个文件，示例：`mget <file_name>/通配符`
* mput：上传多个文件，示例：`mput <file_name>/通配符`

* open：连接到远程 FTP 服务器，示例：`open <host>`
* close / disconnect：断开连接，但不退出 ftp 程序
* bye 或 quit：断开与 FTP 服务器的连接并退出 ftp 程序
* uesr：在连接后重新以其他用户名登录服务器。

* status：查看当前 FTP 各种设置的状态
* ascii：直接切换 ascii 模式（默认为 ascii 模式）
* binary：直接切换 binary 模式
* verbose：详细模式开关，默认为：开启详细模式，详细模式会显示所有 FTP 服务器响应的信息
* bell：响铃开关，当一个文件完成传输时，计算机会发出 “嘀” 的响声
* prompt：交互提示开关
* glob：通配符开关，关闭后，mget，mput 中的 * ？ 将不会解释为通配符
* debug：调试开关
* trace：比 debug 更详细
* hash：进度条
* type：查询或设置文件传输模式 ascii 或 binary


不常用
remotehelp 
quote


#FTP
#文件传输


PS C:\Users\d33pse4> ftp -n 123.56.106.144
连接到 123.56.106.144。
220 (vsFTPd 3.0.5)
200 Always in UTF8 mode.
ftp> d33pse4
无效命令。
ftp> user
用户名 d33pse4
331 Please specify the password.
密码:

230 Login successful.
ftp> ls
200 PORT command successful. Consider using PASV.
150 Here comes the directory listing.
wei
zhang
226 Directory send OK.
ftp: 收到 15 字节，用时 0.00秒 15.00千字节/秒。
ftp> bye
221 Goodbye.

PS C:\Users\d33pse4> ftp -n 123.56.106.144
连接到 123.56.106.144。
220 (vsFTPd 3.0.5)
200 Always in UTF8 mode.
ftp> ls
530 Please login with USER and PASS.
530 Please login with USER and PASS.
ftp> user
用户名 d33pse4
331 Please specify the password.
密码:

230 Login successful.
ftp> ls
425 Use PORT or PASV first.
ftp>