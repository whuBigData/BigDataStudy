### common hdfs opration command

1. format of hadoop command

    ```sh

    hadoop command [genericOptions] [commanfOptions]

    ```

2. common hdfs opration command

    ```sh

    # show info of file specified by <path>
    hadoop fs -ls <path>

    # show info of directory specified by <path>
    # recurse all son files and directories of the directory
    hadoop fs -lsr <path>

    # create a directory specfied by <path>
    hadoop fs -mkdir <path>

    # move file from some directory specified by <src> to directory specified by <dst>
    hadoop fs -mv <src> <dst>

    # copy file or directory from <src> to <dst>
    hadoop fs -cp <src> <dst>

    # show size of file or all son files and directories of directory specified by <path>
    hadoop fs -du <path>

    # show size of file or directory specified by path
    hadoop fs -dus <path>

    # clear the dustbin
    hadoop fs -expunge

    # remove some file specified by <src>
    hadoop fs -rm <src>

    # remode some directory specified by <src>
    # recurse all son files and directories
    hadoop fs -rmr <src>

    # output content of file specified by <path> to terminal
    hadoop fs -cat <path>

    # change the group directory/file specified by <path> belongs to
    # recurse all son files and directories of the directory
    hadoop fs -chgrp [-R] group <path>

    # change the owner of directory/file specified by <path>
    # recurse all son fies and directories of he directory
    hadoop fs -chown [-R] group <path>

    # change change file or directory specified by <path>
    # recurse all son files and directories of directory
    hadoop fs -chmod [-R] <mode> <path>

    # read last one kb data to terminal
    # -f [--follow] continuously monitor last one kb data
    hadoop fs -tail [-f] <path>

    # get info of file or directory specified by <path> satisfied [format]
    # just show the create time of file or directory when command excludes [format] 
    hadoop fs -stat [format] <path>

    # create a empty directory
    hadoop fs -touchz <path>

    # set the number of data's counterpart included in directory pecified by <path>
    # recurse all son files and directoriess
    hadoop fs -setrep [-R] <path> 

    # test file's status
    # -e [--exist]  0: exists, 1: doesn't exist
    # -z [--zero]   0: file is 0 byte, 1: file is not 0 byte
    # -d [--dir]    0: file is not a directory, 1: file is a directory 
    hadoop fs -test -[ezd] <path>

    # output a zip or TxtRecordInputStream file to terminal
    hadoop fs -text <path>

    # copy a file or directory specified by <localsrc> from local file system to hadoop system
    hadoop fs -copyFormLocal <localsrc> <dst>

    # copy a file or directory specified by <target> from hadoop system to local file system
    # -crc: with a crc data when copy local file system
    # -ignorecrc: ignore crc data when copy to local file system
    hadoop fs -copyToLocal [-ignorecrc] [-crc] <target> <localdst>

    # copy a file or directory specified by <localsrc> from local file system to hadoop system
    hadoop fs -put <localsrc> <dst>

    # copy a file or directory specified by <localsrc> to hadoop file system
    # and delete local file or directory when copy complete
    hadoop fs -moveFromLocal <localsrc> <dst>

    # copy a file or directory specified by <src> from hadoop file system to local file system
    hadoop fs -get [ignorecrc] [-crc] <src> <localdst>
    ```