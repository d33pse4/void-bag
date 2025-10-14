# [tmux-列出会话结果解析](../index/tmux.md#tmux-列出会话结果解析)

```
(0) - hello: 3 windows (attached)
(1) ├─> - 0: bash
(2) │   ├─> 0: bash
(3) │   └─> 1: bash*
(4) ├─> - 1: bash-
(5) │   ├─> 0: bash*
(6) │   └─> 1: bash
(7) └─> - 2: [tmux]*Z
(8)     ├─> 0: bash
(9)     └─> 1: bash*
```


- [tmux]\*Z：表示当前所在窗口
- -：表示上一次所在的窗口
- *：表示光窗口

```
d33pse4@d33pse4Debian:~$ tmux ls
hello: 1 windows (created Sun Apr 27 11:21:59 2025) (attached)
```

- hello： 会话名称
-  (created Sun Apr 27 11:21:59 2025)：创建会话时间



#tmux