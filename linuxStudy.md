
### linux(ubuntu) 用户设置

1. 创建用户、 赋予用户权限
    
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



