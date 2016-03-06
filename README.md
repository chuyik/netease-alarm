网易云音乐 - 音乐闹钟
---

![logo](http://7xrl8t.com1.z0.glb.clouddn.com/alarm.png)

想用电脑的网易云音乐来做起床闹钟？试试该脚本吧。   
仅支持 OSX，其他系统欢迎提交 PR。

## 原理
该脚本工作原理很简单，就是自动打开网易云音乐，发送播放歌曲的命令。

## 功能
- 播放前检查人是否在附近   
     怎么判断呢？一般来说，人在手机就在。因此最简单粗暴的方法，就是检查下电脑所在网络的 MAC 地址列表，是否找到你的设备。
- 设置响铃时间、是否仅工作日播放
- 自动调整播放音量（淡入淡出音量）
- 一定时间后停止播放

## 配置

1. 下载代码（请确保系统安装[Node.js](https://nodejs.org/en/download/)）
    ```bash
    $ cd /PATH/TO/PUT/FILES
    $ git clone https://github.com/chuyik/netease-alarm.git
    $ cd netease-alarm & npm install
    ```

2. 打开 [data.yml](data.yml)，按照说明修改配置

3. 测试脚本是否有用   
    如无意外，闹钟会在下一分钟响起来。（如果没响，应该是手机没被扫描到，可以去掉 MAC 地址再试。）
    ```bash
    # 需要输入密码
    $ make test
    ```

4. 将脚本添加至系统计划任务，让闹钟每天都响起来
    ```bash
    # 需要输入密码
    $ make install
    ```

## 注意
1. 如果你的手机是 iPhone，请确保手机夜晚连着充电器，因为手机会进入睡眠模式而无法扫描不到。
2. 运行日志被记录在 logs 文件夹。
