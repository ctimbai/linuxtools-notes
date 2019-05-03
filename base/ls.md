### 1. 列出列表长清单

```sh
ls -l
```



### 2. 显示文件大小

```sh
ls -lh
```



### 3. 按文件大小排序列出

```sh
ls -lhS
```



### 4. 按单位大小列出文件

```sh
ls -l -block-size=M

# 常见的单位有
K = Kilobyte   M = Megabyte   G = Gigabyte   T = Terabyte   P = Petabyte   E = Exabyte   Z = Zettabyte   Y = Yottabyte
```



### 5. 显示隐藏文件

```sh
ls -a
```



### 6. 只列出目录条目

```sh
ls -d */
```



### 7. 不打印所有者信息

```sh
ls -lg
```



### 8. 不打印组信息

```sh
ls -lG
```



### 9. 打印 UID 和 GID

```sh
ls -ln
```



### 10. 打印索引或 `inode` 号

```sh
ls -li
```



### 11. 递归列出子目录

```sh
ls -R
```



### 12. 按修改时间排序

```sh
ls -lt
```



### 13. 列出主目录

```sh
ls ~
```



### 14. 列出父目录

```sh
ls ../
ls ../../
```

