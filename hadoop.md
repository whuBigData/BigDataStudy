
### hadoop 的安装与使用 (ubuntu)

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