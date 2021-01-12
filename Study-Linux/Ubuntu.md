 * @Author: qie
 * @Date: 2021-01-10 10:33:33
 * @Description: A note of Linux-Ubuntu
# Ubuntu����ƪ

[TOC]



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

## Linux����֪ʶ

#### vi&vim�༭��

1. wд�룬q�˳���q!�������˳�

2. ��ݼ�
   1. ������ǰ�� ```yy``` ;������ǰ�����µ�5�� ```5yy```
   2. ɾ����ǰ��```dd``` ;ɾ����ǰ�����µ�����```5dd```
   3. ���ļ��в���ĳ������ ```/�ؼ���``` ���س����ң� ```n```��һ��
   4. ```:set nu```�����ļ��кţ�```set nonu```ȡ��
   5. ��ݼ�G�Ƶ��ĵ��׶ˣ�```gg```�Ƶ��ĵ���ͷ
   6. ```u```��������
   7. �ƶ����ڰ���  ```8 shift+g```
   
#### �ػ�&&����&&ע��

1. ```shutdown```����
   - ```shutdown -h 10``` 10s��ػ�
   - ```shutdown  -r 10 ``` 10s������
2. ```halt```
   - ```halt -p ``` �ػ�
   - ```halt --reboot``` ����
3. ```reboot```����
4. ```logout``` ע��

#### �û��˻���

1. ```useradd```

   ``` shell
   useradd newaccount //����һ���û�newaccount
   useradd -d /home/newaccount newaccount  //����һ���û���ָ����Ŀ¼
   ```

2. ```passwd```

   ```shell
   passwd account 123  //��accountָ������123
   ```

3. ```userdel```

   ```
   userdel newaccount //��ɾ���û�
   userdel -r newaccount //ɾ���û�����Ŀ¼
   ```

4. ```id```

   ```shell
   #��ѯ�û���Ϣ
   id account  //��ѯaccount���˻���Ϣ
   ```

5. ```su```

   ```shell
   #��Ȩ�޸ߵ��û��л���Ȩ�޵͵��û�����Ҫ����
   su �û���
   ```

   

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
# cp ��Ҳ����ʹ��ͨ���
# cp source destination (��source�ļ�����һ�ݲ�����Ϊdestination)
cp test1 test2 
# ��Ŀ���ļ��Ѵ��ڣ�ֱ��ʹ�� cp linux������ʾ��Ӧ���� -i ǿ��ѯ��
cp -i test1 test2
# ���Ƹ�Ŀ¼�����е����ļ�����Ŀ¼
cp -R -i TEST-1 TEST-2
```



## Tips

1. ����ʹ��Tab���Զ�����