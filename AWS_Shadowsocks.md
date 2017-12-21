### 搭建Shadowsocks服务器
   首先需要一个云主机，其实青云的很好嘛，但是还有更好的，http://aws.amazon.com/cn/free/ AWS 有一年的免费使用期限，对于翻墙和自己搞点啥东西还是很方便的，强烈推荐，这中间需要绑定信用卡号，会扣掉一美元，注意不要超过期限了哦，超过了可能会要扣钱的。

   申请下来了以后，创建一个Amazon EC2实例(edhat 默认用户名为ec2-user ubuntu默认用户名为ubuntu)，然后就可以在上面倒腾各种服务了。先开启防火墙吧，在网络与安全里面进行设置，如下图所示，在操作那里点开，编辑入站规则:
   允许所有协议的所有端口


   然后我们来安装 Shadowsocks吧，http://shadowsocks.org/en/download/servers.html，这里列出了所有的服务器版本，各种支持啊，我很高兴的选择了 Node.js 版，先安装 Node.js，可以点这里下载，然后 npm install -g shadowsocks 
当然,如果首次安装,你可能因为缺少一些必要的环境而报错.你可以查看我的另一篇如何安装Node.js和如何搭建Web环境获得帮助.

   搞定！接下来进行配置，我的配置文件在这里/usr/local/lib/node_modules/shadowsocks/config.json
   <pre><code>{
    "server":"0.0.0.0",
    "server_port":8388,
    "local_address":"127.0.0.1",
    "local_port":1080,
    "password":"barfoo!",
    "timeout":600,
    "method":"aes-256-cfb"
}</code></pre>

   命令行参数（服务器端启动命令）
   <pre><code>ssserver -c /etc/shadowsocks.json 如果想在后台一直运行Shadowsocks，启动命令如下：
nohup ssserver -c /etc/shadowsocks.json > /dev/null 2>&1 &
</code></pre>

   备注：关于nohup，是可以让程序在后台运行的命令。（或者可使用screen命令）   
   <code>my: nohup ssserver -c /usr/lib/node_modules/shadowsocks/config.json > /dev/null 2>&1 &</code>
   
   同时可以用命令行参数覆盖 /etc/shadowsocks.json 里的设置：
   <pre><code>sslocal -s 服务器地址 -p 服务器端口 -l 本地端端口 -k 密码 -m 加密方法
ssserver -p 服务器端口 -k 密码 -m 加密方法</code></pre>
   备注：sslocal是客户端程序；ssserver是服务端程序。

   如果要关闭服务，kill掉shadowsocks的进程即可：   
   <code>killall ssserver</code>
   
### 客户端

   搞完了服务器，搞客户端，Shadowsocks 客户端那个多呀，http://shadowsocks.org/en/download/clients.html 都支持。下面说一下 Mac 的配置，其他的一样样的，从上面的链接下载ShadowsocksX，然后启动ShadowsocksX，客户端配置参照下图，IP 填你的云主机的 IP 就 OK 了。
