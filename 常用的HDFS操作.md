### common hdfs opration command

1. format of hadoop command

    ```sh

    hadoop command [genericOptions] [commanfOptions]

    ```

2. common hdfs opration command

    ```

    # show info of files specified by path
    hadoop fs -ls <path>

    # output content of file specified by path to terminal
    hadoop fs -cat <path>

    # -R specify all the son directories and files belongs to directory
    # change the group directory/file specified by path belongs to
    hadoop fs -chgrp [-R] group <path>

    # -R specify all the son directories and files belongs to directory
    # change the owner directory/file
    hadoop fs -chown [-R] group <path>