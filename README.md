
# 2018/05/03/13:21
# 游戏更新完毕,PUBG改变了封包密钥. 等待破解新的封包加密协议的密钥...雷达等待新更新........

After the game is updated, PUBG changes the packet key. Waiting to crack the key of the new packet encryption protocol... Radar waits for a new update........

# ======================================
# 2018/05/03/6:48
升级成1.2+
修复一系列错误.包括雷达运行着无缘无故崩溃等问题.缩小GitHub项目体积 提高git clone的速度.
# ======================================
# 2018/04/30/23:30
 升级成1.2  修复地图放大时出现错位~
 

# ======================================
# 2018/04/30/21:00
由于Pubgmap.io 地图服务器问题,导致地图载入不完全 ,本次更新把地图文件下载在 在服务器内 读取游戏地图

不再从Pubgmap.io调用地图  # 实现地图秒加载~ 

请重新安装雷达,简单暴力 服务器进行重装系统的操作...

修复雷达 敌人 车辆黑色 以及敌人ID错乱等问题
 # ======================================
# 2018/04/27/18:37
Fixed an issue where the enemy could not be displayed.
修复由于游戏版本大更新,导致敌人不在雷达上显示的问题.
# ======================================

#  Cloud Radar1.2+ 安装前记得看更新日志
什么年代了 你还在用虚拟机? 两台电脑? 局域网? JAVA? 用了加速器就失效的雷达?
醒一醒现在是2018年了 Cloud 云服务时代  
只要有浏览器(不限设备 手机电脑 平板随意) 只要有网络(不限网络 手机4G 还是电脑宽带)
打开浏览器输入网址即可享用雷达!

# 测试连接是否正常

下载- [SSTap](https://share.weiyun.com/5yntFxq) 解压打开SSTap

打开后选择代理 右边的+号  添加SS/SSR代理 - 服务器IP就是你服务器的公网IP - 端口和密码就是你自己之前搭建设置的 - 加密协议不要选错了你之前搭建的时候选的是什么就是什么,默认是aes-256-gcm  - 最后下面的 [√] 添加并激活使用


添加完成后 点击+号 右右右边的 闪电标志 测试一下你的SS代理是否正常  如果显示红色字样

检查你SS是否搭建成功 以及你服务器的 SS端口是否开放.

TCP 和 UDP 必须都是绿色字 才算成功.

如果都成功了 表示你的SS代理搭建成功了!

- [使用脚本 少量代码自动搭建雷达教程](#使用脚本搭建教程)


# ======================================

# 安装雷达前 还需要安装nodejs  npm  和 libpcap 


curl https://raw.githubusercontent.com/creationix/nvm/v0.13.1/install.sh | bash
nvm install v9.8.0
nvm alias default v9.8.0



# 安装libpcap

yum -y install gcc-c++ flex bison

wget http://www.tcpdump.org/release/libpcap-1.8.1.tar.gz

tar -zxvf libpcap-1.8.1.tar.gz

cd libpcap-1.8.1

./configure

make && make install




# 最后安装雷达


git clone https://github.com/XiaohuaCN/Cloud-Radar-Plus [更具服务器的带宽 来决定速度快慢]

cd Cloud-Radar-Plus/

npm i

npm i -g pino

npm install -g forever

forever start index.js sniff eth0 XX.XX.XX.XX | pino

(此处的XX填写 你购买的服务器的内网IP )


# 打开浏览器尝试连接雷达

搭建完成雷达后 我们打开浏览器 输入你的 服务器公网IP 也就是你SS的IP 后面加上:20086

如我的公网IP是127.0.0.1 在浏览器内打开的就是 127.0.0.1:20086

然后回车即可看到雷达的网页界面. 如果发现拒绝访问

请检查你的IP是否是你服务器公网的IP  还有就是20086端口是否映射了(如果是放通全部端口的服务器 就不用映射了).






