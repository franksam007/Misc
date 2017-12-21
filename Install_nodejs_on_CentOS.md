CentOS 下安装 Node.js

1. 下载源码，你需要在https://nodejs.org/en/download/下载最新的Nodejs版本，本文以v8.9.0为例:  
    <pre><code>cd /usr/local/src/
    wget https://npm.taobao.org/mirrors/node/v8.9.0/node-v8.9.0-linux-x64.tar.xz</code></pre>

2. 解压源码   
   <code>tar zxvf node-v8.9.0-linux-x64.tar.xz</code>

3. 编译安装   
   <pre><code>cd node-v8.9.0-linux-x64
   ./configure --prefix=/usr/local/node-v8.9.0-linux-x64
   make
   make install</code></pre>

4. 配置NODE_HOME，进入profile编辑环境变量   
   <code>vim /etc/profile</code>

   设置nodejs环境变量，在 export PATH USER LOGNAME MAIL HOSTNAME HISTSIZE HISTCONTROL 一行的上面添加如下内容:

   <pre><code>#set for nodejs
   export NODE_HOME=/usr/local/node/0.10.24
   export PATH=$NODE_HOME/bin:$PATH</code></pre>   
   :wq保存并退出，编译/etc/profile 使配置生效   
   <code>source /etc/profile</code>   

   验证是否安装配置成功   
   <code>node -v</code>   
   输出 v8.9.0 表示配置成功   

   npm模块安装路径   
   <code>/usr/local/node/8.9.0/lib/node_modules/</code>
