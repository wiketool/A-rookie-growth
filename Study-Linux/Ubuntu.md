 * @Author: qie
 * @Date: 2021-01-10 10:33:33
 * @Description: A note of Linux-Ubuntu
# Ubuntu养成篇



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

#### 用户账户类

1. ```useradd```

   ``` shell
   useradd newaccount //创建一个用户newaccount
   useradd -d /home/newaccount newaccount  //创建一个用户并指定主目录
   useradd -g 用户组 用户名  //创建一个用户并指定用户组
   ```

2. ```passwd```

   ```shell
   passwd account 123  //给account指定密码123
   ```

3. ```userdel```

   ```
   userdel newaccount //仅删除用户
   userdel -r newaccount //删除用户及主目录
   ```

4. ```id```

   ```shell
   #查询用户信息
   id account  //查询account的账户信息
   ```

5. ```su```

   ```shell
   #从权限高的用户切换到权限低的用户不需要密码
   su 用户名
   ```

6. ```exit``` 退出当前用户

7. ```whoami``` 查询当前用户

8. 用户组

   ```shell
   # 添加用户组
   groupadd 组名
   # 删除用户组
   groupdel 组名
   # 修改用户的主组
   usermod -g 用户组 用户名
   # 将用户添加至组
   gpasswd -a 用户名 用户组
   # 将用户从组中移除
   groupwd -d 用户名 用户组
   ```

   

## 基本命令语法

#### ```pwd```

```shell
# 显示当前工作目录的绝对路径
```

#### ``` mkdir && rmdir ```

```shell
# 创建目录
mkdir 目录名
# 创建多级目录
mkdir -p 目录/目录
# 删除空目录
rmdir 目录
# 删除非空目录
rm -rf 目录
```



#### ```cd```

```shell
# cd 命令可以切换目录
cd /usr/bin
cd bin
# '/'开头的路径为绝对路径
# 否则为相对路径
cd ~ 或者 cd 直接回到家目录
```

```shell
# .表示当前目录
# .. 表示当前目录的上一级目录
# 假设现在有目录/usr,目录下有downloads、bin
cd /usr
# 切换至downloads
cd ./downloads
# 切换至bin
cd ../bin
```

#### ```ls```

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
ls -l
# 过滤输出列表( ? 代表一个字符  * 代表零个或多个字符)
ls -l l?b*
# ls -F -R = ls -FR

```

#### ```touch```

```shell
# 创建文件
touch 文件1 文件2
```

#### ```cp```

```shell
# cp 中也可以使用通配符
# cp source destination (将source文件复制一份并命名为destination)
cp test1 test2 
# 若目标文件已存在，直接使用 cp linux不会提示，应加上 -i 强制询问
cp -i test1 test2
# 复制该目录下所有的子文件及子目录
cp -R -i TEST-1 TEST-2
```

#### ```rm```

```shell
# 删除文件
rm 文件名
# 删除文件夹
rm -r 文件夹
```

#### ```mv```

```shell
# 移动文件（）
mv 旧文件路径/文件名 新文件路径
# 文件重命名
mv 旧文件路径/文件名 新文件路径/新文件名
```

#### ```cat```

```shell
# 以只读模式打开文件
cat 文件名
# 显示行号
cat -n 文件名 
# 分页浏览 
cat 文件名 | more
```

#### ```more```

```shell
# 查看文件内容
more 文件名
```

#### ```less```

```shell
# 查找文件内容
less 文件名
/[字符串]  # n 向下查找  N 向上查找
```

#### ``` >  &&  >> ```

```shell
# 将ls -l 的内容追加至test.txt中
ls -l >> test.txt
# 将ls -l 的内容覆盖写入至test.txt中
ls -l > test.txt
# 将文件一的内容追加至文件二末尾
cat 文件一 >> 文件二
```

#### ```echo```

```shell
echo [输出内容]
```

#### ```head && tail```  

```shell
# 显示文件头部多少行的东西
head -n 行数 文件名
# 显示文件末尾多少行的东西
tail -n 行数 文件名
# 实时跟踪文件末尾变化
tail -f 文件名
```

#### ```ln```

```shell
# 软连接
ln -s 原文件或者目录 软链接名
# 在软链接下使用 pwd 时，看到的仍然是软链接的目录
```

#### ```history```

```shell
# 显示最近的10条历史命令
history 10
# 选择编号为 190 的命令
!190
```

#### ```date```

```shell
# 显示当前时间年月日时分秒
date '+%Y %m %d %H %M %S'
# 设置系统时间
date -s '2018 10 10 11 22 22'
```

#### ```cal```

```shell
# if 'Command 'cal' not found'
sudo apt-get install ncal
# 显示2021年日历
cal 2021
```

#### ```find```

```shell
# 查找/home下的名为3.c的属于jc用户的大小为10字节的文件
find /home -name 3.c -user jc -size 10
# 查找大于1k(M)的文件
find ./ -size +1k(M)
```

#### ```locate```

```shell
# sudo apt-get install locate
updatedb # 建立索引数据库
locate 文件名
```

#### ```grep```

```shell
# 管道符'|'将前一个指令的处理结果输出传递给后一个指令处理
# 在test中查找TEST
cat test | grep -n TEST ( -n 显示匹配行及行号 -i 忽略大小写)
```

#### ```gzip && gunzip```

```
gzip 文件 # -k 保持源文件不被更改
```



## Tips

1. 可以使用Tab键自动补齐