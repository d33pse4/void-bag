
# [tmux-对窗口的操作](../index/tmux.md#tmux-对窗口的操作)


## Ttmux-在会话中创建窗口mux

```
ctrl + b c
或
tmux new-window
或
tmux new-window -n <window-name>

```

## tmux-关闭会话中的窗口


```
ctrl + d
或
ctrl + b &
或	
tmux kill-window -t
```


## tmux-会话中切换窗口

```
切换到上一个window
ctrl + b p

切换到下一个window
ctrl + b n

切换到指定编号的window
ctrl + b <num>
tmux select-window -t <window-name/window-num>
```

## tmux-从列表中选择窗口


```
ctrl + b w
```

## tmux-重命名会话中的窗口

```
ctrl + b ,

tmux rename-window <new-name>
```
































