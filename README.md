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
$ find /-type d-print | awk'{print length($0), $0}’ | sort-n | tail-1
```

Find the deepest file

```Shell
$ find /-type d-print | awk'{print length($0), $0}’ | sort-n
```

Delete all .class files

```Shell
$ find . -name “*.class” -print0 | xargs -0 rm
```

Find broken symlinks

```Shell
$ find -L . -type l
$ find -L /target/dir -type l -exec ls -l {} \; 
$ find /target/dir -type l ! -exec test -e {} \; -print
```

Remove broken symlinks

```Shell
$ find -L /path/to/check -type l -delete
$ find /target/dir -type l ! -exec test -e {} \; -delete 
```


