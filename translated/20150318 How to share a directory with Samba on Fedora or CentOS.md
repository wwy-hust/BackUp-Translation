�����Fedora��CentOS��ʹ��Samba�����ļ���
================================================================================
��������ڼ�������ǰ칫��������ͬ�ĵ���֮�乲���ļ����Ѳ���ʲô�������ˡ������������£��ִ�����ϵͳͨ�������ļ�ϵͳ�ķ�ʽʹ�õ��Լ����ݵĽ�����ü򵥶�͸��������������Ļ����м���΢���Windows����Linux����ô��һ�������ļ���Ŀ¼�ķ�ʽ����ͨ��һ����ƽ̨�����ļ�����Э��,SMB/CIFS��Windows��Ȼ��֧��SMB/CIFS��LinuxҲͨ����Դ�����Sambaʵ����SMB/CIFSЭ�顣

����ƪ�����У����ǽ�չʾ**���ʹ��Samba�����ļ���**������ʹ�õ�Linuxƽ̨��**Fedora��CentOS**����ƪ���·�Ϊ�Ĳ��֡����ȣ�������Fedora/CentOS�����°�װSambe�����ţ�����������ε���SELinux�ͷ���ǽ����������Samba���ļ�����������ǽ������ʹ��Samba�������ļ��С�

### ����1����Fedora��CentOS�ϰ�װSamba ###

���ȣ���װSamba�Լ�����һЩ���������á�

����Samba�Ƿ��Ѿ���װ������ϵͳ�У�

    $ rpm -q samba samba-common samba-client 

������������û���κ����������ζ��Samba��δ��װ����ʱ��Ӧʹ���������������װSamba��

    $ sudo yum install samba samba-common samba-client 

������������һ�������������й���ı����ļ��С�����ļ���Ӧ����Samba����ķ�ʽ������Զ�̵��û��������ָ���У����ǻ��ڶ����ļ���'/'�д�������ļ��У���ˣ���ȷ��������Ӧ��Ȩ�ޡ�

    $ sudo mkdir /shared 

�������������home�ļ����ڴ��������ļ��У����磬~/shared���������뼤��SELinux��Samba��home�ļ��й���ѡ����彫�ں����ᵽ��

�ڴ���/shared�ļ��к������ļ���Ȩ���Ա�֤�����û����Է�������

    $ sudo chmod o+rw /shared 

��������������û��Ը��ļ���ӵ��дȨ�ޣ�����Ҫ�Ƴ������е�'w'ѡ�

    $ sudo chmod o+r /shared 

������������һ�����ļ������ԡ�����ļ����Ա�������֤Samba�Ĺ����Ѿ������ء�

    $ sudo touch /shared/file1 

### ����2��ΪSamba����SELinux ###

��������������Ҫ�ٴ�����SELinux����Fedora��CentOS���а���SELinux��Ĭ�Ͽ����ġ�SELinux������ȷ�İ�ȫ�����²�����Samba��ȡ���޸��ļ����ļ��С������磬����'samba_share_t'���Ա�ǩ����

���������Ϊ�ļ���������ӱ�Ҫ�ı�ǩ��

    $ sudo semanage fcontext -a -t samba_share_t "<directory>(/.*)?" 

��<directory>�滻Ϊ����֮ǰΪSamba�������ı����ļ��У����磬/shared����

    $ sudo semanage fcontext -a -t samba_share_t "/shared(/.*)?" 

���Ǳ���ִ��restorecon�����������޸ĵı�ǩ���������£�

    $ sudo restorecon -R -v /shared 

![](https://farm9.staticflickr.com/8584/16652774078_2055f45f70_b.jpg)

Ϊ��ͨ��Samba����������home�ļ����ڵ��ļ��У����Ǳ�����SELinux�п�������home�ļ��е�ѡ���ѡ��Ĭ�ϱ��رա�����������ܴﵽ��Ч�����������δ��������home�ļ��У���ô�����������ò��衣

    $ sudo setsebool -P samba_enable_home_dirs 1 

### ����3��ΪSamba���÷���ǽ ###

��������������򿪷���ǽ��SambaΪ������Ҫ��TCP/UDP�˿ڡ�

�������ʹ��firewalld�����磬��Fedora��CentOS7�£�������������������õ��޸�Samba��صķ���ǽ����

    $ sudo firewall-cmd --permanent --add-service=samba 

������ڷ���ǽ��ʹ��iptables�����磬CentOS6���߸���İ汾��������ʹ���������������Samba��Ҫ������Ķ˿ڡ�

    $ sudo vi /etc/sysconfig/iptables 

----------

    -A RH-Firewall-1-INPUT -m state --state NEW -m tcp -p tcp --dport 445 -j ACCEPT
    -A RH-Firewall-1-INPUT -m state --state NEW -m udp -p udp --dport 445 -j ACCEPT
    -A RH-Firewall-1-INPUT -m state --state NEW -m udp -p udp --dport 137 -j ACCEPT
    -A RH-Firewall-1-INPUT -m state --state NEW -m udp -p udp --dport 138 -j ACCEPT
    -A RH-Firewall-1-INPUT -m state --state NEW -m tcp -p tcp --dport 139 -j ACCEPT

Ȼ������iptables����

    $ sudo service iptables restart 

### ����4������Samba���� ###

����Ĳ�����������Samba�Խ������ļ��е���ΪSamba�����ļ��С�

ʹ���ļ��༭����Samba�����ļ����������������ӵ��ļ���ĩβ��

    $ sudo nano /etc/samba/smb.conf 

----------

    [myshare]
    comment=my shared files
    path=/shared
    public=yes
    writeable=yes

�����������ڵ��ı������磬"myshare"����Samba�������Դ�����֣�����������Զ��������ȡSamba����

����Samba�û��ʻ������ǹ��غ͵���Samba�ļ�ϵͳ������ġ����ǿ���ʹ��smbpasswd����������һ��Samba�û���ע�⣬Samba�û��ʻ�������Linux�û��������Ѵ��ڵġ����������ʹ��smbpasswd���һ�������ڵ��û������᷵��һ���������Ϣ��

���������ʹ���κ��Ѵ��ڵ�Linux�û���ΪSamba�û���������������ϵͳ�д���һ���µ��û���Ϊ��ȫ������������û��ĵ�¼�ű�Ϊ/sbin/nologin�����Ҳ��������û���home�ļ��С�

����������У��������ڴ���һ������"sambaguest"���û������£�

    $ sudo useradd -M -s /sbin/nologin sambaguest
    $ sudo passwd sambaguest 

![](https://farm9.staticflickr.com/8702/16814479366_53f540d3ba_b.jpg)

�ڴ���һ�����û���ʹ��smbpasswd�������Samba�û������������ѯ��һ������ʱ�������Լ���һ����ͬ�ڸ��û������롣

    $ sudo smbpasswd -a sambaguest

4. ����Samba���񣬲����Samba�����Ƿ������С�

    $ sudo systemctl enable smb.service
    $ sudo systemctl start smb.service
    $ sudo systemctl is-active smb 

![](https://farm8.staticflickr.com/7607/16652984770_622f24bccc_b.jpg)

ʹ��������������鿴Samba�й�����ļ����б�

    $ smbclient -U sambaguest -L localhost 

![](https://farm8.staticflickr.com/7281/16220411103_06bf585901_b.jpg)

����������Thunar�ļ��������д�ȡSamba�����ļ����Լ���file1���п������ƵĽ�ͼ��ע�⣬Samba�Ĺ������ݿ���ͨ����Thunar��ͨ��"smb://<samba-server-IP-address>/myshare"�����ַ����ȡ��

![](https://farm8.staticflickr.com/7644/16218011174_c8b34fcedc_b.jpg)

--------------------------------------------------------------------------------

via: http://xmodulo.com/share-directory-samba-fedora-centos.html

���ߣ�[Kristophorus Hadiono][a]
���ߣ�[wwy-hust](https://github.com/wwy-hust)
У�ԣ�[У����ID](https://github.com/У����ID)

������ [LCTT](https://github.com/LCTT/TranslateProject) ԭ�����룬[Linux�й�](http://linux.cn/) �����Ƴ�

[a]:http://xmodulo.com/author/kristophorus
