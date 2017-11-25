##### hadoop 的安装与使用 (ubuntu)


1. 创建 hadoop 用户

    ```sh

    $ adduser hadoop          # 创建 hadoop 用户
    $ vim /etc/sudoers        # 打开用户权限文件

    ```
    在 /etc/sudoers 文件中加入

    ```sh

    hadoop ALL=(ALL:ALL) ALL  # 赋予 hadoop 用户 root 权限

    ```


2.  Java 安装

    ```sh

    $ sudo add-apt-repository ppa:webupd8team/java    # 获取最新的个人软件包档案源，将其添加到 apt 库中， 并自动导入公钥
    $ sudo apt-get update                             # 更新
    $ sudo apt-get install oracle-java8-installer     # 安装 oracle-java8-installer
    $ sudo apt-get install oracle-java8-set-default   # 如果在前一条命令安装时自动安装了，则不需要

    ```

    Java 安装默认地址:     **/usr/lib/jvm/java-8-oracle**


3. SSH 登录权限设置

    ```sh

    $ sudo -i -u hadoop                    # 切换到 hadoop 用户
    $ ssh-keygen -t rsa -P ''               # 免密码生成公钥、私钥对  -p (--password)
    $ cd ~/.ssh                            # 切换到公钥、私钥对目录
    $ cat id_rsa.pub >> authorized_keys    # 将本机 hadoop 用户的公钥保存到本机 hadoop 用户， 使得 ssh 连接本机能够成功
    $ chmod 600 authorized_keys            # 设置 authorized_keys 文件权限为 可读可写
    $ chmod 700 ~/.ssh                     # 设置 ~/.ssh 文件权限为 可读可写可执行
    $ vim /etc/ssh/ssh_config              # 打开 /etc/ssh/ssh_config 文件

    ```

    在 /etc/ssh/ssh_config 文件中 添加:

    ```sh

    RSAAuthentication yes       # 允许使用 ssh 登录
    PubkeyAuthentication yes    # 允许使用公钥
    PermitRootLogin yes         # 允许 root 登录
    PasswordAuthentication no   # 不需要密码验证登录

    ```

    ```sh
    
    $ service sshd restart      # 重启 ssh 服务
    $ ssh localhost             # 使用 ssh 协议连接本机， 若不需要输入密码，则免密码连接成功
    
    ```

    若显示则 ssh 权限配置成功：

    ```sh
    
    Last login: Mon Nov 20 09:59:16 2017 from 127.0.0.1    # 类似 Last login

    ```

4. 安装单机 Hadoop

   到 [hadoop网址(1.2.1版本)](http://mirrors.hust.edu.cn/apache/hadoop/common/hadoop-1.2.1/hadoop-1.2.1-bin.tar.gz) 下载 hadoop 1.2.1 版本代码</br>

   到 下载目录 解压下载包到 /usr/local/hadoop 目录中</br>

    ```sh

    $ sudo mkdir /usr/local/hadoop                                  # 创建 hadoop 文件
    $ sudo tar -zxvf hadoop-1.2.1-bin.tar.gz -C /usr/local/hadoop   # 解压 hadoop 文件到 /usr/local/hadoop
    $ sudo chown hadoop:hadoop /usr/local/hadoop                    # 设置 /usr/local/hadoop 的拥有这为 hadoop 组 的 hadoop 用户
    $ cd /usr/local/hadoop/hadoop-1.2.1                                          

    ```

    更改 conf 目录下面的 hadoop-env.sh（hadoop 运行环境文件） 配置文件 </br>