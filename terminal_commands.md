## List memory size of folders

List memory usage of all drives

    df -h

See the current mount availability

    df -h .

See size of folder

    cd folder_name
    du -hs

See size of subfolders

    cd folder_name
    du -h --max-depth=1 | sort -hr


## List permission to folder

    ls -l

## Unzip archive

Unzip specific folder in archive

    ! unzip archive.zip "parent/target_folder/*" -d ./parent/target_folder
