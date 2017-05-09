EVE China Mac 启动器 Parsec

世界服 EVE 在 Mac 下运行很顺畅，可是国服却没有 Mac 版本。因为我习惯用 Mac，虚拟机和 Bootcamp 体验不爽，就琢磨做一个 Mac 的启动器。几天研究下来，终于完成。EVE China 在 Mac 下运行也极其顺畅，硬件加速、声音、输入、中文字体等都完美支持，玩了几天后感觉稳定了，就分享给大家。

Parsec 基于 Mono Frameworks 开发而成，EVE China 运行在 Wine 环境中。下面详细讲安装的过程：

1、安装 Mono Frameworks
http://www.mono-project.com/download/ 下载安装；
也可以通过 brew 安装：brew install mon。
安装完成后，将 /Library/Frameworks/Mono.framework/Commands 加入 $PATH

2、安装 Wine 环境 2.01
到 https://www.winehq.org/ 下载安装；
也可以 brew install wine。
安装完成后，将 /usr/local/bin 加入 $PATH。
运行 winecfg，将自动创建 ~/.wine/ 环境。

3、配置 wine 的中文环境，参照
https://www.lulinux.com/archives/362
我直接将微软雅黑对应的字体改名成 simsun.ttf，simsun.ttc, simfang.ttc，安装上面的网址修改注册表和复制到 windows/Fonts 目录下即可

4、下载 EVE 国服完整版解压到 ~/.wine/drive_c/EVE

5. 在 shell 环境下运行 regedit C盘.reg，以完成 SharedCache 数据文件的目录配置

6. 一切完成后，即可启动 Parsec Launcher：
命令行：mono Parsec.exe path_of_exefile username password [-opengl]
mono：mono 的调入器
Parsec.exe：我写的启动器
path_of_exefile：EVE China官方文件包里的一个文件，exefile.exe
username：用户名
password：密码
[-opengl]：指定的话则启动opengl模式，硬件加速效果很好，可以不指定

比如：
/Library/Frameworks/Mono.framework/Commands/mono ./Parsec.exe /Users/acamar/.wine/drive_c/EVE/Client/bin/exefile user pass -opengl

7. 不提供源码，以免被做成脚本破坏游戏平衡。

8. 懂点 Shell Script 或者 AppleScript 的，可以将这个启动器包装成一个 app，启动起来就更简单了。

在 iMac 2011 下，可以开到 2560x1440 最大分辨率，抗锯齿等特效打开都运行顺畅。 Macbook Pro 2016 运行在 2560x1600 效果全开也非常稳定流畅。

本人游戏内角色 Acamar，有问题可以直接加我。

