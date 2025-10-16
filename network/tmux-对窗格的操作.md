# [tmux-对窗格的操作](../index/tmux.md#tmux-对窗格的操作)

## tmux-在窗口中左右划分窗格

```
ctrl + b %
或
tmux split-window -h
```


## tmux-在窗口中上下划分窗格

ctrl + b "
或
tmux split-window

## tmux-关闭当前窗格

```
ctrl + d
或
ctrl + b x
```


## tmux-按箭头方向调整pane大小

```
ctrl + b ctrl + <arrow key>
```


## tmux-在各个窗格中移动光标方向键切换窗格


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


## tmux-序号切换窗格

```
ctrl + b q 0-9
```


## tmux-向前旋转窗格

```
ctrl + b ctrl + o 向前旋转窗格
```


## tmux-将垂直水平布局的两个窗格改为水平垂直方向

```
ctrl + b 空格
```


## tmux-交换窗格位置

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


## tmux-显示time


```
ctrl + b t
```


## tmux-将当前窗格拆分为一个独立窗口

```
ctrl + b !
```

## tmux-当前窗格全屏显示再使用依次会变回原来大小


```
ctrl + b z
```


## tmux-如何进行翻页

```
进入翻页模式
ctrl + b [

然后，使用 pageUP、pageDown、UP、Down进行翻页
```


## tmux-重新加载当前的配置

```
tmux source-file ~/.tmux.conf
```


























