# bash 学习笔记

## 变量

```sh
$var='abc def'
```


把命令输出的结果直接赋给变量：

```sh
$var=\`date\`
```

变量嵌入：

```
$echo hello$var

$echo ${var}hello
```

字符串中要引用变量，必须用双引号，如：

```sh
$var=world  
$echo "hello $var"
```

## 数值运算，要将运算的数字放在$(())中

```sh
$result=$(((1+2)*3))

$var=1  
$result=$(($var+1*3))
```


$?保存返回值，$0,$1,$2表示第几个参数

## 函数

```sh
function f() {

}  
f
```

## 跨脚本调用用 source

## 逻辑判断
- 大于等于：-gt
- 小于等于：-lt
- 等于：-eq
- 不等于：-ne
- 文本相同：ab = bc
- 文本不同：ab != bc
- 按照词典顺序,一个文本在一个文本之前：abc > tce
- 按照词典顺序,一个文本在一个文本之后：abc < tce
- 检查一个文件是否存在： $test –e a.out; echo $? 
- 检查一个文件是否存在，而且是普通文件： $test –f file.txt; echo $? 
- 检查一个文件是否存在，而且是目录文件： $test –d myfiles; echo $? 
- 检查一个文件是否存在，而且是软连接： $test –L a.out; echo $? 
- 检查一个文件是否可读： $test –r file.txt; echo $? 
- 检查一个文件是否可写： $test –w file.txt; echo $? 
- 检查一个文件是否可执行： $test –x file.txt; echo $? 


结合与 或 非

```sh
! expression  

expression1 –a expression2  

expression1 –o expression2  
```

## 条件判断

```sh
if [ $var = 'root' ] //注意括号两边有空格  
then  
xxx  
fi  
```


## case 语句

```sh
#!/bin/bash

var=`whoami`
echo "You are $var"

case $var in
root)
echo "You are God."
;;
vamei)
echo "You are a happy user."
;;
*)
echo "You are the Others."
;;
esac
```

## 循环结构
### while

```sh
#!/bin/bash

now=`date +'%Y%m%d%H%M'`
deadline=`date --date='1 hour' +'%Y%m%d%H%M'`

while [ $now -lt $deadline ]
do
  date
  echo "not yet"
  sleep 10
  now=`date +'%Y%m%d%H%M'`
done

echo "now, deadline reached"
```

### for
```sh
#!/bin/bash

for var in `ls log*`
do
  rm $var
done
```

常和 seq 使用  
seq 1 2 10  
\>> 1 3 5 7 9

```sh
#!/bin/bash

total=0

for number in `seq 1 1 100`
do
  total=$(( $total + $number ))
done

echo $total
```



只有while的时候，加个：

```sh
#!/bin/bash

total=0
number=1
while :
do
  if [ $number -gt 100 ]
  then
    break
  fi

  total=$(( $total + $number ))
  number=$(($number + 1))
done

echo $total
```