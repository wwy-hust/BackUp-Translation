��Ubuntu 14.10�ϰ�װLinux-Dash(����Web�ļ�ع���)
================================================================================

Linux-Dash��һ������GNU/Linux�����ģ��Ϳ����ļ���Ǳ��̡���װ���������ʼʹ�ðɣ�Linux Dash�Ľ����ṩ�����ķ����������йؼ���Ϣ����ϸ��ͼ���ɼ�����Ϣ����RAM������ʹ���ʡ����硢��װ��������û������е��̵߳ȡ����е���Ϣ�������࣬������ͨ����ҳ�������еİ�ť�����κ�һ���С�Linux Dash���������Ƚ��ļ�⹤�ߣ�����ʮ���ʺ�Ѱ���������������ײ����Ӧ�õ��û���

### Linux-Dash�Ĺ��� ###

ʹ��һ������Web��Ư�����Ǳ��̽�������ط�������Ϣ

ʵʱ������ļ��RAM�����ء�����ʱ�䡢�������á��û����������ϵͳ״̬��

�ɲ���ʽ��Ϊ��������װ�����������Apache2/niginx + PHP��

ͨ��������϶��������пؼ�

֧�ֶ������͵�linux������

### ��ǰ�ؼ��б� ###

- ͨ����Ϣ
- ƽ������
- RAM
- ����ʹ����
- �û�
- ���
- IP
- ��������
- ������
- ������
- ��־

### ��Ubuntu server 14.10�ϰ�װLinux-Dash ###

��������Ҫȷ������װ��[Ubuntu LAMP server 14.10][1]������������Ҫ��װ����İ���

    sudo apt-get install php5-json unzip

��װ���ģ�����Ҫ��apache2��ʹ�ܸ�ģ�飬��������Ҫʹ���������������apache2��������

    sudo service apache2 restart
    
��������Ҫ����linux-dash�İ�װ������װ����

    wget https://github.com/afaqurk/linux-dash/archive/master.zip

    unzip master.zip

    sudo mv linux-dash-master/ /var/www/html/linux-dash-master/

����������Ҫʹ��������������ı�Ȩ�ޣ�

    sudo chmod 755 /var/www/html/linux-dash-master/

����������Է���http://serverip/linux-dash-master/�ˡ���Ӧ�ûῴ����������������

![](http://www.ubuntugeek.com/wp-content/uploads/2015/02/1.png)

![](http://www.ubuntugeek.com/wp-content/uploads/2015/02/2.png)

--------------------------------------------------------------------------------

via: http://www.ubuntugeek.com/install-linux-dash-web-based-monitoring-tool-on-ubntu-14-10.html

���ߣ�[ruchi][a]
���ߣ�[wwy-hust](https://github.com/wwy-hust)
У�ԣ�[У����ID](https://github.com/У����ID)

������ [LCTT](https://github.com/LCTT/TranslateProject) ԭ�����룬[Linux�й�](http://linux.cn/) �����Ƴ�

[a]:http://www.ubuntugeek.com/author/ubuntufix
[1]:http://www.ubuntugeek.com/step-by-step-ubuntu-14-10-utopic-unicorn-lamp-server-setup.html
