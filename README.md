# A Compilation of Useful Bash Commands #


List all the files in a repository and print out their name

```Shell
$ for f in *.xlsm; do echo "$f"; done
```

Replace a pattern in the names of the files in the repository

```Shell
$ for f in *.xlsm; do echo "`echo $f | sed s/Juin/Novembre/`"; done
```

Rename the files in a repository by replacing a pattern in the name

```Shell
$ for f in *.xlsm; do mv "$f" "`echo $f | sed s/Juin/Novembre/`"; done
```

Find the longest path - directory

```Shell
$ find / -type d -print | awk '{print length($0), $0}' | sort -n | tail -1
```

Find the deepest file in the current directory and sub-directories and sort it increasing

```Shell
$ find / -type d -print | awk '{print length($0), $0}' | sort-n
```

Delete all .class files in the current directory and sub-directories

```Shell
$ find . -name "*.class" -print0 | xargs -0 rm
```

Find broken symlinks in the current directory and sub-directories

```Shell
$ find -L . -type l
$ find -L . -type l -exec ls -l {} \;
$ find . -type l ! -exec test -e {} \; -print
```

Remove broken symlinks in the current directory and sub-directories

```Shell
$ find -L . -type l -delete
$ find . -type l ! -exec test -e {} \; -delete
```

Recursively replace CRLF with LF

```
$  find source_folder/ -type f -print0 | xargs -0 dos2unix
``
