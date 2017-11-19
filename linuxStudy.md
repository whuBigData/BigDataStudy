
### linux(ubuntu) 用户设置
    
* 创建用户
    $: 普通管理员
    #: 系统管理员
    
        ```sh
    
        $ useradd username    # 创建用户，不会创建用户主目录、用户同名组
        $ adduser username    # 创建用户，会创建用户主目录、 同名用户组    ----- ubuntu 最好用起创建用户
        $ passwd username     # 设置用户密码
        
        $ sudo -i -u username # 切换到用户 username 下
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


### cat 命令：

    ```sh

    $ cat filename                        # 一次显示整个文件
    $ cat > filename                      # 从键盘创建一个文件
    $ cat [options] file1 file2 > file    # 将几个文件合为一个文件
    
    ```

    options 说明：

    ```c

    -n(--number)             // 由 1 开始对所有行数进行编号
    -b(--number-nonblank)    // 与 **-n** 类似， 不过对于所有空白行不编号
    -s(--squeeze-blank)      // 将遇到连续两行以上的空白行合为 1 行编号
    -v(--show-nonprinting)

    ```





