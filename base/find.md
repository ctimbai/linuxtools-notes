# find 指南

查找 home 目录下的文件名或目录为 hello 的：

```sh
find /home -name hello*
```

查找根目录下 h 开头第二个字符任意，第三个是 m，后面是任意的字符：

```sh
find / -name h?m*
```

查找根目录下查询文件大于 1000000K 的文件

```sh
find / -size +1000000K
```

查找目录下所有文件中是否含有某个字符串，并且只打印出文件名：

```sh
find .|xargs grep -rin "IBM" -l
# -l 打印文件名
```



查找 txt 和 pdf 文件：

```sh
find . ( -name "*.txt" -o -name "*.pdf" ) -print
```



正则方式查找 txt 和 pdf

```sh
find . -regex ".*(.txt|.pdf)$"
```

- iregex：忽略大小写



查找所有非 txt 文本

```sh
find . ! -name "*.txt" -print
```



打印当前目录的文件（深度为 1）：

```sh
find . -maxdepth 1 -type f
```



