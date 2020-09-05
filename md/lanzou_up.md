## 脚本介绍

很早之前，为了实现自动制作便携版并上传 qBittorret、qBittorretEE 到蓝奏云网盘，我就特地写了这个脚本来解决上传文件到蓝奏云网盘的问题。  

该脚本作用很简单，**自动登陆并上传文件到蓝奏云指定文件夹**，方便 Linux 系统用户使用，或其他脚本调用。  

因为一开始我只是自用，所以功能就只有上传文件，至于以后会不会添加其他功能，就...咕咕咕🕊

### 脚本版本

**最新版本：** v1.0.0

### 系统要求

所有 Linux 系统均支持。

****

## 下载安装

先下载脚本并赋予执行权限，先不要运行，还需要简单配置一下。

``` bash
wget -N --no-check-certificate https://shell.xiu2.xyz/lanzou_up.sh && chmod +x lanzou_up.sh
```

****

## 使用方法

### 账号配置

使用 vim 或 nano 来编辑脚本，下面以 nano 为例。  
``` bash
nano lanzou_up.sh

# 打开脚本文件后，可以看到脚本头部有以下三行内容。
# 修改 XXX 为你的蓝奏云用户名和密码。
# 然后按下 Ctrl+X 并回车两下即可保存。

USERNAME="XXX" # 蓝奏云用户名
PASSWORD="XXX" # 蓝奏云密码
TOKEN="XXX" # 微信推送链接 Token

# 脚本支持推送错误消息至微信，但是需要配置 TOKEN，支持以下两种，自行了解，不需要可留空或保留 XXX。
# pushplus(默认) http://pushplus.hxtrip.com
# Server酱 https://sc.ftqq.com/3.version
```

账号配置完毕后，就可以先试一试能不能正常上传文件了！  
首先，你需要知道 **文件夹 ID** 才能将文件上传到这个文件夹。  

### 获取文件夹ID

网页端登陆蓝奏云，找到目标文件夹，右键文件夹名称 - 检查。
如下图所示，红框中的就是文件夹 ID 了 (880498)。  

![蓝奏云获取文件夹ID](https://shell.xiu2.xyz/img/lanzou_up-01.png)

### 上传文件

知道 文件夹 ID 了，那就先随便找个文件（注意文件后缀要满足蓝奏云要求，且文件不大于 100MB），然后就可以上传了：  

``` bash
# 格式：
bash lanzou_up.sh "文件名" "文件路径" "文件夹 ID"

# 示例
bash lanzou_up.sh "233.zip" "/root/233.zip" "880498"
```

****

### 文件位置
 - **Cookie文件：**/root/lanzouyun_cookie.txt  

****

## 更新日志
 
#### 2020年09月06日，版本 v1.0.0 :id=100
 - **1. 发布** 第一个版本。