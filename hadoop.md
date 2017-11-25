# hadoop 的安装与使用 (ubuntu)

   本人原本 ubuntu 用户： **xj (shell 上显示 xj@xj)***</br>
   切换到 hadoop 用户后： **hadoop(shell 上显示 hadoop@xj)**</br>


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
    $ ssh-kegen -t rsa -P ''               # 免密码生成公钥、私钥对  -p (--password)
    $ cd ~/.ssh                            # 切换到公钥、私钥对目录
    $ cat id_rsa.pub >> authorized_keys    # 将本机 hadoop 用户的公钥保存到本机 hadoop 用户， 使得 ssh 连接本机能够成功
    $ chmod 600 authorized_keys            # 
    $ chmod 700 ~/.ssh                     #
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
