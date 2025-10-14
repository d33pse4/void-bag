
# [tmux-在各个窗格中移动光标方向键切换窗格](../index/tmux.md#tmux-在各个窗格中移动光标方向键切换窗格)


```
ctrl + b <arrow key>

切换窗格快捷键
# 切换上一个pane
ctrl + b ;
# 切换下一个pane
ctrl + b o

# 切换上方pane
tmux select-pane -U

# 切换下方pane
tmux select-pane -D

# 切换左边pane
tmux select-pane -L

# 切换右边pane
tmux select-pane -R
```



#tmux