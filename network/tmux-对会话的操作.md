# # [tmux-对会话的操作](../index/tmux.md#tmux-对会话的操作)

## # tmux-创建会话

```
tmux
tmux new
```

## # tmux-创建指定名称的会话

```
tmux new -s hello
tmux new-session -s hello
```

## # tmux-的快捷键的前缀键是什么

tmux 执行一些快捷键操作时，需要先按下“前缀键”，`Ctrl + b`，再按其他快捷键，快捷键功能才能生效

## # tmux-退出会话

```
ctrl + b : kill-session
tmux kill-session -t <session-name>
```

## # tmux-挂起会话

```
ctrl + b d
tmux detach
```

## # tmux-恢复会话

```
tmux a
tmux attach
```

## # tmux-恢复指定名称的会话

```
tmux a -t <session-name>
tmux attach -t <session-name>
tmux attach-session -t <session-name>
```

## # tmux-列出所有会话并切换

```
ctrl + b s
```
再次按 q 或 ESC，则退出展示，可通过 UP、DOWN 选择会话，Enter 确认

```
tmux ls
tmux list-session
```

```
ctrl + b ( 切换上一个会话
ctrl + b )  切换下一个会话
tmux switch -t <session-name>
```

## # tmux-列出会话结果解析

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
- *：表示光标所在窗格

```
d33pse4@d33pse4Debian:~$ tmux ls
hello: 1 windows (created Sun Apr 27 11:21:59 2025) (attached)
```

- hello： 会话名称
-  (created Sun Apr 27 11:21:59 2025)：创建会话时间

## # tmux-重命名当前会话

```
ctrl + b $
tmux rename-session -t <old-name> <new-session>
```

## # 标签

#tmux

## # 反链

