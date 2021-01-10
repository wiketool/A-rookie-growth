<!--
 * @Author: qie
 * @Date: 2021-01-10 10:33:33
 * @Description: A note of Linux-Ubuntu
-->
# Ubuntu����ƪ
## ��װ

1. ���������װ����

2. ���ú��û���������

3. ��Ubuntu�д�Terminal
   ```shell
   sudo passwd
   ```
   ���ú�root�������
   ```shell
   su root
   ```
   �л���root�˻�
   
4. ���� xshell (��root�˻���)
   ```shell
   sudo apt-get install openssh-server
   ```
   
5. Ȼ��Ϳ��Կ��ĵ���ˣ��

## ���������﷨

#### ```cd``` ����

1. ```cd```�л�Ŀ¼

   ```shell
   # cd ��������л�Ŀ¼
   cd /usr/bin
   cd bin
   # '/'��ͷ��·��Ϊ����·��
   # ����Ϊ���·��
   ```

2. ```shell
   # .��ʾ��ǰĿ¼
   # .. ��ʾ��ǰĿ¼����һ��Ŀ¼
   # ����������Ŀ¼/usr,Ŀ¼����downloads��bin
   cd /usr
   # �л���downloads
   cd ./downloads
   # �л���bin
   cd ../bin
   ```

#### ```ls``` ����

```shell
# �г���ǰĿ¼�µ��ļ�
ls
# �г��ļ��������ļ����ļ���
ls -F
# �г��ļ����������أ�
ls -a
# �г���ǰĿ¼����Ŀ¼�������ļ�
ls -R
# ��ʾ�ļ���ϸ��Ϣ
ls -a
# ��������б�( ? ����һ���ַ�  * ������������ַ�)
ls -l l?b*
# ls -F -R = ls -FR

```

#### ```touch```����

�ڱ�Ŀ¼�����ļ�

#### ```cp```��������ļ���

```shell
# cp source destination (��source�ļ�����һ�ݲ�����Ϊdestination)
cp test1 test2 
# ��Ŀ���ļ��Ѵ��ڣ�ֱ��ʹ�� cp linux������ʾ��Ӧ���� -i ǿ��ѯ��
cp test1 test2 -i

```

