第一种方案（比第二种方案简单便宜）：
1.点此链接：https://www.socketpro.link/aff/92019
2.点击：GET SOCKETPRO
3.选择支付方式以及你的邮箱。
4.支付
5.使用


第二种方案：
1.vultr购买

首先进行注册：https://www.vultr.com/?ref=7186642


然后进入paypel充值界面。

充值之后，点击左侧的Servers选择服务器，可选的地点较多，对于我们中国用户来说，东京和新加坡延迟会好一点。


然后系统我们选择debian8x64主机，根据自己的需要选择合适的套餐。

然后点击Deploy now，就可以部署服务器了。

2.通过Xshell 连接VPS
点击左侧的Servers，可以看到我们已经有一台可用的服务器，点击我们刚购买的服务器，显示running为正常运行状态，进入之后可以看到服务器的详细信息，服务器的登陆密码password下方有个复制按钮可以点，初始服务器密码比较复杂可以防止入侵，尽量不要更改。每次使用密码的时候复制即可。

先安装好Xshell5，新建会话，输入服务器的ip，端口不用更改，然后点确定。

然后选择创建好的会话，点连接，选择接受并保存，用户名输入：root。

然后会提示输入密码，将复制好的密码粘贴进去即可。勾选记住密码，这样以后可以方便的进行登陆。

登陆成功后，Xshell5界面最后一行会显示root@xxxxxxxx:~# 这些。

3.shadowsocksr服务端的部署
首先使用以下命令升级系统。复制该命令到Xshell5，粘贴之后回车，（粘贴快捷键不是ctrl+c，请注意）。

apt-get update

等待执行完毕。

然后复制shadowsocksr的安装命令，和上方的运行方式一样，粘贴之后回车。

wget -N –-no-check-certificate https://raw.githubusercontent.com/91yun/shadowsocks_install/master/shadowsocksR.sh && bash shadowsocksR.sh
或者
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh && chmod +x ssr.sh && bash ssr.sh


端口默认为8989，如果你想更改，可以自行输入其他端口，直接按回车的话，默认就为8989端口。

看到最后的：Press any key to start … or Press Ctrl+C to cancel 这句话之后按任意键开始执行，如果想取消就按Ctrl+C。

几分钟后，如果倒数第二行出现Enjoy it!就表示安装成功了，你就可以使用了。不过后面还需要稍微部署一下。


------------------------------------------------
第4条锐速加速功能慎用，容易被封。

4.锐速serverspeeder的安装
使用锐速加速能非常快的完成服务器网络优化，提供外网良好体验。

复制下面命令到Xshell5，粘贴之后回车。

wget -N –-no-check-certificate https://raw.githubusercontent.com/91yun/serverspeeder/master/serverspeeder-all.sh && bash serverspeeder-all.sh

以下是几个锐速常用命令：

重启锐速 /serverspeeder/bin/serverSpeeder.sh restart
启动锐速 /serverspeeder/bin/serverSpeeder.sh start
停止锐速 /serverspeeder/bin/serverSpeeder.sh stop
锐速状态 /serverspeeder/bin/serverSpeeder.sh status

5.PC端shadowsocksr的使用
下载shadowsocksr客户端，如果是win7系统打开dotnet2.0，如果是win8/10系统打开dotnet4.0应用程序即可。
然后依次输入ip，端口，加密类型，密码等。
加密类型以及协议可以在/etc/shadowsocks.json文件中查看。

然后右键点击windows右下方的shadowsocksr图标，设置系统代理模式为：PAC模式。
之后再将服务器 -> (empty group) -> 你的服务器ip 选择为你的服务器。
再然后选择代理规则为绕过局域网和大陆。否则可能导致访问国内网站速度较慢。
最后选择PAC -> 更新PAC为GFWList。
这样就能随意访问外网了。


