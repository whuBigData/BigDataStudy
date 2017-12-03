### common hdfs opration command

1. format of hadoop command

    ```sh

    hadoop command [genericOptions] [commanfOptions]

    ```

2. common hdfs opration command

    ```sh

    # show info of files specified by path
    hadoop fs -ls <path>

    # show info of all files and directores belonging to directory specified by path
    hadoop fs -lsr <path>

    # create a directory specfied by path
    hadoop fs -mkdir <path>

    # move file from some directory specified by <src> to directory specified by <dst>
    hadoop fs -mv <src> <dst>
    hadoop fs -rm <src>
    hadoop fs -rmr <src>

    # output content of file specified by path to terminal
    hadoop fs -cat <path>

    # -R specify all the son directories and files belongs to directory
    # change the group directory/file specified by path belongs to
    hadoop fs -chgrp [-R] group <path>

    # -R specify all the son directories and files belongs to directory
    # change the owner directory/file
    hadoop fs -chown [-R] group <path>

    # 
    hadoop fs -tail [-f] <path>
    hadoop fs -stat [format] <path>

    hadoop fs -touchz <path>

    hadoop fs -copyFormLocal <localsrc> <dst>
    hadoop fs -copyToLocal [-ignorecrc] [-crc] <localsrc> <dst>
    hadoop fs -put <localsrc> <dst>
    hadoop fs -moveFromLocal <localsrc> <dst>


    hadoop fs -setrep [-R] <path> 
    hadoop fs -test -[ezd] <path>
    hadoop fs -text <path>
    ```