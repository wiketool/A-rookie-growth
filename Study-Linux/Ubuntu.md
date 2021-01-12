 * @Author: qie
 * @Date: 2021-01-10 10:33:33
 * @Description: A note of Linux-Ubuntu
# Ubuntu养成篇

[TOC]



## 安装

1. 从虚拟机安装镜像

2. 设置好用户名和密码

3. 在Ubuntu中打开Terminal
   ```shell
   sudo passwd
   ```
   设置好root的密码后
   ```shell
   su root
   ```
   切换至root账户
   
4. 配置 xshell (在root账户下)
   ```shell
   sudo apt-get install openssh-server
   ```
   
5. 然后就可以开心的玩耍了

## Linux基本知识

#### vi&vim编辑器

1. w写入，q退出，q!不保存退出

2. 快捷键
   1. 拷贝当前行 ```yy``` ;拷贝当前行以下的5行 ```5yy```
   2. 删除当前行```dd``` ;删除当前行向下的五行```5dd```
   3. 在文件中查找某个单词 ```/关键字``` ；回车查找； ```n```下一个
   4. ```:set nu```设置文件行号，```set nonu```取消
   5. 快捷键G移到文档底端，```gg```移到文档开头
   6. ```u```撤销动作
   7. 移动到第八行  ```8 shift+g```
   
#### 关机&&重启&&注销

1. ```shutdown```命令
   - ```shutdown -h 10``` 10s后关机
   - ```shutdown  -r 10 ``` 10s后重启
2. ```halt```
   - ```halt -p ``` 关机
   - ```halt --reboot``` 重启
3. ```reboot```重启
4. ```logout``` 注销



## 基本命令语法

#### ```cd``` 命令

1. ```cd```切换目录

   ```shell
   # cd 命令可以切换目录
   cd /usr/bin
   cd bin
   # '/'开头的路径为绝对路径
   # 否则为相对路径
   ```

2. ```shell
   # .表示当前目录
   # .. 表示当前目录的上一级目录
   # 假设现在有目录/usr,目录下有downloads、bin
   cd /usr
   # 切换至downloads
   cd ./downloads
   # 切换至bin
   cd ../bin
   ```

#### ```ls``` 命令

```shell
# 列出当前目录下的文件
ls
# 列出文件并区分文件和文件夹
ls -F
# 列出文件（包含隐藏）
ls -a
# 列出当前目录及子目录下所有文件
ls -R
# 显示文件详细信息
ls -a
# 过滤输出列表( ? 代表一个字符  * 代表零个或多个字符)
ls -l l?b*
# ls -F -R = ls -FR

```

#### ```touch```命令

在本目录创建文件

#### ```cp```命令（复制文件）

```shell
# cp 中也可以使用通配符
# cp source destination (将source文件复制一份并命名为destination)
cp test1 test2 
# 若目标文件已存在，直接使用 cp linux不会提示，应加上 -i 强制询问
cp -i test1 test2
# 复制该目录下所有的子文件及子目录
cp -R -i TEST-1 TEST-2
```



## Tips

1. 可以使用Tab键自动补齐