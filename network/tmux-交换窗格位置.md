
# [tmux-交换窗格位置](../index/tmux.md#tmux-交换窗格位置)

交换窗格位置的前提，需要先了解 tmux 的窗格是如何排序的，排序原则是：以列排序，按列升序

```
当前窗格与上一个窗格交换位置
ctrl + b {

当前窗格与下一个窗格交换位置
ctrl + b }

所有pane向前移动一个位置
ctrl + b ctrl + o

所有pane向后移动一个位置
ctrl + b alt + o

当前pane上移
tmux swap-pane -U

当前pane下移
tmux swap-pane -D
```
