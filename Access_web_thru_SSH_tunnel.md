1. 建立一个海外虚拟主机，生成Public/Private键对，启动SSH服务
2. 本机利用SSH客户端（XShell），建立SSH隧道。创建tunnel把本地的指令通过隧道传到本地的一个端口，再用主机监听这个端口，从而实现代理服务器。
   左边选择“隧道”，添加dynamic(socks4/5)类型的tunnel，端口任意，例如选择7777
3. 浏览器设置代理端口；最好使用Chrome浏览器加上SwitchyOmega或SwitchySharp等代理管理插件，这样可以实现有规则地使用代理，即上Google等被墙网站使用代理，上百度这种就直接连接；   
   以Chrome浏览器插件SwitchyOmega为例（Proxy SwitchySharp的最新版本）；   
   代理服务器作如下选择：（socks5协议，代理端口一定要和之前选的端口相同）   
   创建规则如下：   
     分享一个能用的规则列表网址https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt   
   保存，设置SwitchyOmega为自动切换模式。   
   
