# inode-njit

njit iNode 802.1x client for Linux

支持iNode 7.0

## 源码来源

1.直接

[https://github.com/tignioj/njit-client-script/tree/change-md5](https://github.com/tignioj/njit-client-script/tree/change-md5)

2.间接

[http://www.right.com.cn/forum/thread-217637-1-1.html](http://www.right.com.cn/forum/thread-217637-1-1.html)

[https://github.com/bitdust/njit8021xclient](https://github.com/bitdust/njit8021xclient)

3.源头

[https://github.com/liuqun/njit8021xclient](https://github.com/liuqun/njit8021xclient)

（感谢以上英雄；其中，[@tignioj](https://github.com/tignioj)，提供了inode7.0的version和key的信息

## 安装

仅以Arch Linux为例：

1. 安装 `base-devel` 组

    `sudo pacman -Sy base-devel`
2. 获取源码

    `git clone https://github.com/milkysilk/inode-njit.git`
3. 进入目录

    `cd inode-njit`
4. 运行

    `autoreconf --install`
5. 运行

    `./configure`
6. 运行

    `make`
7. 运行

    `sudo make install`

完成安装

## 使用

1. 运行 `sudo njit-client [username] [password] [eno1] [version] [key]` 即可；

2. 注意：
    * 网卡名为连接校园网的网卡名称，一般是名称为 `eno1` 的有线网卡，具体请使用 `ifconfig` 查找（Arch Linux使用 `ifconfig` 需要安装 `net-tools` ）
    * 7.0版本对应的version和key分别是 `CH\\u0011V7.00-0106` 和 `Oly5D62FaE94W7` (有两个\的原因它在shell下需要转义)
    * 7.1版本对应的version是 `CH\\x11V7.00-0313` ，key同上
    * 可以给运行命令设置别名，如将 `alias inode7.0='sudo njit-client username password eno1 CH\u0011V7.00-0106 Oly5D62FaE94W7'` 添加到 `～/.bashrc`，然后在终端输入 `inode7.0` 即可

3. 程序会输出一些调试信息，其中大部分信息不用理会
    只需关注如果包括 `[*] Server: Success.` 这样一行提示即为802.1X认证成功

## 更多

[http://wiki.ubuntu.org.cn/南京工程学院802.1X客户端](http://wiki.ubuntu.org.cn/南京工程学院802.1X客户端)

[http://www.cnblogs.com/bitpeach/p/4092806.html](http://www.cnblogs.com/bitpeach/p/4092806.html)
