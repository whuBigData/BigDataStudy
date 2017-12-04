
### linux(ubuntu) 用户设置

```c

    $: 普通管理员</br>
    #: 系统管理员</br>

```

* user命令：</br></br>

    ```sh

    # useradd命令（添加用户）
    # -g(--group)       指定用户所在的用户组
    # -u(--uid)         指定用户 id
    # -e(--expire)      指定用户期满时间

    $ useradd [-g group| -u uid| -e expire] username    # 创建用户，不会创建用户主目录、用户同名组
    $ adduser [-g group| -u uid| -e expire] username    # 创建用户，会创建用户主目录、 同名用户组



    # usermod 命令（修改用户）

    $ usermod -l optUser srcUser         #
    $ usermod -g group user              #
    $ usermod -d dir user                #


    # userdel 命令（删除用户）
    $ userdel [-r] user

    # 修改用户密码
    $ passwd username     # 设置用户密码

    # 切换用户
    $ sudo -i -u username # 切换到用户 username 下

    # 退出当前用户
    $ exit                # 退回到默认用户

    ```




* 赋予用户 root 权限

    ```sh

    $ vim /etc/sudoers

    ```
    在 /etc/sudoers 文件中加入

    ```sh

    username ALL=(ALL) ALL  # 将 root 权限赋予用户 username

    ```

* chown 命令

### chmod 命令


### cat 命令：

* 命令说明

    ```sh


    # -n(--number)              由 1 开始对所有行数进行编号
    # -b(--number-nonblank)     与 **-n** 类似， 不过对于所有空白行不编号
    # -s(--squeeze-blank)       将遇到连续两行以上的空白行合为 1 行编号
    # -v(--show-nonprinting)


    $ cat [-n| -b| -s| -v] filename                        # 一次显示整个文件
    $ cat > filename                      # 从键盘创建一个文件
    $ cat [options] file1 file2 > file    # 将几个文件合为一个文件

    ```


### ssh (secure shell) 说明：

* 生成 ssh 公钥、私钥对

    ```sh

    $ ssh-keygen -t rsa -P ‘’      # 使用 rsa 算法生成密钥对
    $ ssh-keygen -t dsa -P ‘’      # 使用 dsa 算法生成密钥对
    $ ssh-keygen -t rsal -P ‘’     # 使用 rsal 算法生成密钥对

    ```
    -p (--password) [**'' 代表 不需要密码**]</br></br>
    生成 密钥对 的默认路径 **～/.ssh**</br>
    公钥： **id_rsa.pub**</br>
    私钥： **id_rsa**


    [rsa 算法原理1](http://www.ruanyifeng.com/blog/2013/06/rsa_algorithm_part_one.html)</br>
    [rsa 算法原理2](http://www.ruanyifeng.com/blog/2013/07/rsa_algorithm_part_two.html)</br>



### tail
tail [-f] [-c number] [-n number] file
