# Files

## chmod
```sh
#      for   actioon  param
chmod [ugoa]  [-+=]  [rwxXst]
```

1. ugoa - user | group | other | all(default)
2. -+= - remove | add | set
3. rwxXst - read | write | execute | execute dir | set id on execution | set ugo
4. 4 - read, 2 - write, 1 - exec.

> [!NOTE]
> See inodes - `ls -i`


## tar
```sh
Examples:
  tar -cf archive.tar foo bar  # Create archive.tar from files foo and bar.
  tar -tvf archive.tar         # List all files in archive.tar verbosely.
  tar -xf archive.tar          # Extract all files from archive.tar.

 Main operation mode:
  -A, --catenate, --concatenate   append tar files to an archive
  -c, --create               create a new archive
      --delete               delete from the archive (not on mag tapes!)
  -d, --diff, --compare      find differences between archive and file system
  -r, --append               append files to the end of an archive
      --test-label           test the archive volume label and exit
  -t, --list                 list the contents of an archive
  -u, --update               only append files newer than copy in archive
  -x, --extract, --get       extract files from an archive
```


## links
**Soft link** - points to original file `ln -s file link`
**Hard link** - store the same data as linked file and inode number `ln file link`
