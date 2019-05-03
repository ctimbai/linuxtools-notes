## 基本命令

## 常用案例

### CPU 占用最多的前 10 个进程

```sh
ps auxw|head -1;ps auxw|sort -rn -k3|head -10
```



### 内存消耗最多的前 10 个进程

```sh
ps auxw|head -1;ps auxw|sort -rn -k4|head -10
```



### 虚拟内存使用最多的前 10 个进程

```sh
ps auxw|head -1;ps auxw|sort -rn -k5|head -10
```

### 根据参数排序

```sh
ps auxw --sort=rss
ps auxw --sort=%cpu
```
