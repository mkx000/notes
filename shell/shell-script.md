---
author:马凯旋
---

[toc]

### Shell script 评判标准
* The most important criteria must be a clear, readable layout
* Second is avoiding unnecessary commands

### built-in Shell commands
* *cd* : change directory
* *read* : shell 内置命令，读取一个变量值
* *source*: 在当前的 shell 中执行脚本

### 变量

* 变量未赋值之前认为是空值（空字符串？）
* **shell 与 其他的 shell 不共享environment**  每执行一次 shell script，当前的 shell 会自动 spawn a new shell 执行这个 script，执行完毕就会摧毁它的 environment。**shell script 执行完毕以及退出当前的 interactive shell 都会 destroy 对应的 environemt**，所以 environment 中的变量也会消失。
* using **curly brackets** to indictate the start and end of a variable，看下面的例子

``` bash
# 下面的代码是错误的
#!/bin/sh
echo "What is your name?"
read USER_NAME
echo "Hello $USER_NAME"
echo "I will create you a file called $USER_NAME_file"
touch $USER_NAME_file
# 下面的代码是正确的
echo "What is your name?"
read USER_NAME
echo "Hello $USER_NAME"
echo "I will create you a file called ${USER_NAME}_file"
touch "${USER_NAME}_file"
```

### 通配符






### 转义字符
* **\\** is used to escape " , $, `，and \ characters, even when they're in double quotes



### for and while 循环
```bash
#!/bin/sh
for i in 1 2 3 4 5
do
  echo "Looping ... number $i"
done

# 打印 1 ./* 2 goodbye，*取决于当前目录
#!/bin/sh
for i in hello 1 * 2 goodbye 
do
  echo "Looping ... i is set to $i"
done

# loops until you typed "bye"
#!/bin/sh
INPUT_STRING=hello
while [ "$INPUT_STRING" != "bye" ]
do
  echo "Please type something in (bye to quit)"
  read INPUT_STRING
  echo "You typed: $INPUT_STRING"
done

#!/bin/sh
while :
do
  echo "Please type something in (^C to quit)"
  read INPUT_STRING
  echo "You typed: $INPUT_STRING"
done

# This reads the file "myfile.txt", one line at a time, into the variable "$input_text". 
#!/bin/sh
while read input_text
do
  case $input_text in
        hello)          echo English    ;;
        howdy)          echo American   ;;
        gday)           echo Australian ;;
        bonjour)        echo French     ;;
        "guten tag")    echo German     ;;
        *)              echo Unknown Language: $input_text
                ;;
   esac
done < myfile.txt # 把myfile.txt当作输入

# 小技巧：{}的使用
mkdir rc{0,1,2,3,4,5,6,S}.d
ls -ld {,usr,usr/local}/{bin,sbin,lib}
```


### test ( [ is a built-in program like cd)
```bash
$ type [
[ is a shell builtin
$ which [
/usr/bin/[
$ ls -l /usr/bin/[
lrwxrwxrwx 1 root root 4 Mar 27 2000 /usr/bin/[ -> test
# 上面说明 [ 是一个programm
# so it must be surrounded by spaces:
if [$foo = "bar" ] # wrong
if [ $foo = "bar" ] # correct, 区别在于一个空格
```

```bash
# [ or test 用法
1、
if [ ... ]
then
  # if-code
else
  # else-code
fi
2、
if [ ... ]; then
  # do something
fi
3、
if  [ something ]; then
 echo "Something"
 elif [ something_else ]; then
   echo "Something else"
 else
   echo "None of the above"
fi
```

