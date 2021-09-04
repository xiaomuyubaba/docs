# 在软件市场安装常用软件

- WPS
- 金山词霸
- Visual Studio Code
- IntelliJ IDEA 社区版
- 福昕PDF阅读器
- MySQL Workbench

# 安装JDK

1. 安装openjdk8：`sudo apt-get install openjdk-8-jdk`
2. 查看jdk安装目录:
```
jin@jin:~$ ll /usr/bin/java
lrwxrwxrwx 1 root root 22 8月  29 15:03 /usr/bin/java -> /etc/alternatives/java
jin@jin:~$ ll /etc/alternatives/java
lrwxrwxrwx 1 root root 46 8月  29 15:03 /etc/alternatives/java -> /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java
```
3. 安装后发现openjdk里没有javafx包，删除openjdk：
```
sudo apt-get autoremove openjdk-8-jdk
```
4. 下载`oracle-jdk`： `https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html`
```
https://edelivery.oracle.com/akam/otn/java/jdk/8u301-b09/d3c52aa6bfa54d3ca74e617f18309292/jdk-8u301-linux-x64.tar.gz
```
5. 将jdk拷贝到指定目录并解压：
```
cd /usr/lib/jvm
sudo mv ~/Downloads/jdk-8u301-linux-x64.tar.gz .
sudo tar -zxvf jdk-8u301-linux-x64.tar.gz
```
6. 在 `/etc/profile` 文件末尾加上环境变量：
```
export JAVA_HOME=/usr/lib/jvm/jdk1.8.0_301
export JRE_HOME=${JAVA_HOME}/jre
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH
```
7. 使环境变量生效：`source /etc/profile`
8. 检查java命令：
```
java -version
jconsole
jvisualvm
jstack
```

# 安装MySQL

1. 安装MySQL数据库，并启动服务
```
# 安装服务器
sudo apt-get install default-mysql-server

# 安装客户端
sudo apt-get install default-mysql-client

# 启动mysql服务
service mysql start
# 查看mysql服务状态
service mysql status
```
2. 登录数据库，修改root密码
```
sudo mysql -u root

# 设置root用户密码为“root”(注意分号别丢)
MariaDB [(none)]> GRANT ALL PRIVILEGES ON *.* TO root@localhost IDENTIFIED BY "root"; 

# 刷新权限
flush privileges; 
```
3. 退出后再登录就需要密码了

# 安装Git并连接Github

1. 安装Git并设置命令别名
```
sudo apt-get install git-all

git config --global alias.st status
git config --global alias.cmt "commit -m"
git config --global alias.br branch
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```
2. 生成访问Github所需的key
```
ssh-keygen -o
ll ~/.ssh/
cat ~/.ssh/id_rsa.pub
```
3. 将`id_rsa.pub`的内容拷贝到Github账户设置中的ssh-key页面
