
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

sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
sudo apt-get install oracle-java8-set-default