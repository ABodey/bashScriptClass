# rsync
Rsync (remote synchornization) is a way to copy and synchronize files and directories either locally or remotely. It is efficient and only syncs new or changed files so can be used for backup. It also can use a remote protocol to only send the changed blocks and bytes.

## syntax
rsync options source destination

## options
 - **-v** verbose
 - **-r** copies data recursively (does not preserve timestamps and permissions)
 - **-a** archive mode, allows copying files recursively and preserve symbolic links, file permissions, user and group ownerships, and timestamps.
 - **-z** compress file data
 - **-h** human readable
 - **--progress** show progress of the synchornization
 - **--include** and **--exclude** to control the files that are copied
 - **--delete** delete the files and directories in the destination that no longer exist in the source. Look at the man pages for a variety of delete options, the standard is to delete before the transfer but you can do it after, during, delay, etc.
 - **--remove-source-files** deletes all the files from source after the transfer to destination.
 - **--dry-run** does not do a transfer but shows what would happen. Useful if you are doing something that would destroy things (such as delete or remove-source-files).
 - **-W** synch whole files, not just bytes and blocks
 - **--bwlimit** set the bandwidth limit for the transfer if the network is congested.
 - **-b** or **--backup** make a backup of any changed files. You can use **--suffix** to override the default suffix of `~` and/or you can specify the backup directory with **--backup-dir=DIR**.

There are also options for adjustment of times (sometimes useful when doing Windows as that OS doesn't keep track of time properly! ;-) )

## source and destination

When using "/" at the end of source, rsync will copy the content of the last folder.
When not using "/" at the end of source, rsync will copy the last folder and the content of the folder.

When using "/" at the end of destination, rsync will paste the data inside the last folder.
When not using "/" at the end of destination, rsync will create a folder with the last destination folder name and paste the data inside that folder.

### local
For a local file or directory just give the path to the node such as `file.tar` if in current working directory, `~/Documents/` to reference something in the home directory or ``/tmp/backup/`` to reference from the root.

### remote over rsync
The syntax for a remote location is

  `user@host:path`

This will require that the user be known on the host and rsync will request the password for that user. The path can be an absolute path from root or reference the local home directory of the user that is logging into the system. Most of the time rsync puts the user into their home directory.

This syntax uses the rsync demon.

### remote over ssh 
To specify the protocol use the `-e` option.

An example

`rsync -avzhe ssh user@192.168.1.132:path`

### include and exclude
These allow the control of what is included and excluded.

An example that includes all files that start with R and exclude all others.

```rsync -avze ssh --include 'R*' --exclude '*' root@192.168.0.101:/var/lib/rpm/ /root/rpm```

** References
 - [Rsync local and remote](https://www.tecmint.com/rsync-local-remote-file-synchronization-commands/)
 - [Backup Files in Linux](https://www.linux.com/learn/how-backup-files-linux-rsync-command-line)
 - [rsync examples](http://www.comentum.com/rsync.html)
