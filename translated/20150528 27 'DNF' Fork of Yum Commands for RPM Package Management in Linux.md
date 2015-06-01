27��Linux������������ߡ�DNF����Yum�ķ�֧��������
================================================================================
DNF��Dandified YUM�ǻ���RPM�ķ��а����һ������������ߡ���������Fedora 18�г��֣�������������е�Fedora 22�������[YUM���߼�][1]��

![](http://www.tecmint.com/wp-content/uploads/2015/05/linux-dnf-command-examples.jpg)

DNF�����ڸ���YUM��ƿ���������ܡ��ڴ�ռ�á�����������ٶȺ�����������档DNFʹ��RPM��libsolv��hawkey����а�������������δԤװ��CentOS��RHEL 7�У���������ͨ��yum��װ����ͬʱʹ�ö��ߡ�

��Ҳ�����Ķ��������DNF����Ϣ��

- [ʹ��DNFȡ��Yum�����ԭ��][2]

���µ�DNF�ȶ��汾��2015��5��11�շ�����1.0����д��ƪ����֮ǰ���������Լ�����DNF֮ǰ�汾����Ҫ��Python��д������GPL v2���֤������

### ��װDNF ###

����Fedora 22�ٷ��Ѿ����ɵ���DNF����DNF������RHEL/CentOS 7��Ĭ�ϲֿ��С�

Ϊ����RHEL/CentOSϵͳ�а�װDNF������Ҫ���Ȱ�װ�Ϳ���epel-release�ֿ⡣

    # yum install epel-release
    ��
    # yum install epel-release -y

���ܲ���������ʹ��yumʱ����'-y'ѡ���Ϊ��û��ǿ���ʲô����װ������ϵͳ�С���������Դ˲������⣬��������ʹ��'-y'ѡ�����Զ����İ�װ�������û���Ԥ��

��������ʹ��yum�����epel-realease�ֿⰲװDNF����

    # yum install dnf

����װ��dnf���һ�����չʾ27��ʵ�õ�dnf��������ӣ��Ա���������׺͸�Ч�Ĺ������RPM���ķ��а档

### 1. ���DNF�汾 ###

�������ϵͳ�ϰ�װ��DNF�汾��

    # dnf --version

![���DNF�汾](http://www.tecmint.com/wp-content/uploads/2015/05/Check-DNF-Version.gif)

### 2. �г�������DNF�ֿ� ###

dnf�����е�'repolist'ѡ���ʾ��ϵͳ�����п����Ĳֿ⡣

    # dnf repolist

![������п����Ĳֿ�](http://www.tecmint.com/wp-content/uploads/2015/05/Check-All-Enabled-Repositories.gif)

### 3. �г����п����͹رյ�DNF�ֿ� ###

'repolist all'ѡ���ʾ��ϵͳ�����п���/�رյĲֿ⡣

    # dnf repolist all

![�г����п���/�رյĲֿ�](http://www.tecmint.com/wp-content/uploads/2015/05/Check-All-Repositories.gif)

### 4. ��DNF�г����п��õ����Ѱ�װ������� ###

'dnf list'����г����вֿ������п��õ����������Linuxϵͳ���Ѱ�װ���������

    # dnf list

![List All Packages using DNF](http://www.tecmint.com/wp-content/uploads/2015/05/List-All-Packages.png)

### 5. ��DNF�г������Ѱ�װ������� ###

����'dnf list'����г����вֿ������п��õ���������Ѱ�װ���������Ȼ��������һ��ʹ��'list installed'ѡ�ֻ�г��Ѱ�װ���������

    # dnf list installed

![List All Installed Packages](http://www.tecmint.com/wp-content/uploads/2015/05/List-Installed-Packages.png)

### 6. ��DNF�г����п��õ������ ###

���Ƶģ�������'list available'ѡ���г����п����Ĳֿ������п��õ��������

    # dnf list available

![List Available Packages using DNF](http://www.tecmint.com/wp-content/uploads/2015/05/List-Available-Packages.png)

### 7. ʹ��DNF��������� ###

�������̫������밲װ������������֣���������£�������ʹ��'search'ѡ��������ƥ����ַ������磬nano�����ַ������������

    # dnf search nano

![Search Package by Word](http://www.tecmint.com/wp-content/uploads/2015/05/Search-Package.gif)

### 8. �鿴�ĸ�������ṩ��ĳ���ļ�/������������ ###

dnf��ѡ��'provides'�ܲ����ṩ��ĳ���ļ�/���������������������磬������������Ǹ�������ṩ����ϵͳ�е�'/bin/bash'�ļ�������ʹ�����������

    # dnf provides /bin/bash

![Find File Sub Package](http://www.tecmint.com/wp-content/uploads/2015/05/Find-Package-Sub-Package.gif)

### 9. ʹ��DNF���һ�����������ϸ��Ϣ ###

��������ڰ�װһ�������ǰ֪��������ϸ��Ϣ��������ʹ��'info'�����һ�����������ϸ��Ϣ�����磺

    # dnf info nano

![Check Package Information with DNF](http://www.tecmint.com/wp-content/uploads/2015/05/Check-Package-Information.gif)

### 10. ʹ��DNF��װ����� ###

�밲װһ����nano���������ֻ������������������Ϊnano�Զ��Ľ���Ͱ�װ���е�������

    # dnf install nano

![Install Package using DNF](http://www.tecmint.com/wp-content/uploads/2015/05/Install-Package-DNF.gif)

### 11. ʹ��DNF����һ������� ###

������ֻ�����һ���ض��İ������磬systemd�����ұ���ϵͳ��ʣ����������䡣

    # dnf update systemd

![Update a Specific Package](http://www.tecmint.com/wp-content/uploads/2015/05/Update-a-Package.gif)

### 12. ʹ��DNF���ϵͳ���� ###

���ϵͳ�а�װ������������ĸ��¿��Լ򵥵�ʹ��dnf���У�

    # dnf check-update

![Check For System Update](http://www.tecmint.com/wp-content/uploads/2015/05/Check-For-System-Update.gif)

### 13. ʹ��DNF��װϵͳ�����е������ ###

������ʹ���������������������ϵͳ�������Ѱ�װ���������

    # dnf update
    ��
    # dnf upgrade

![Update System](http://www.tecmint.com/wp-content/uploads/2015/05/Update-System.gif)

### 14. ʹ��DNF���Ƴ�/ɾ��һ������� ###

��������dnf������ʹ��'remove'��'erase'ѡ�����Ƴ��κβ���Ҫ���������

    # dnf remove nano
    ��
    # dnf erase nano

![Remove Package in Linux](http://www.tecmint.com/wp-content/uploads/2015/05/Remove-Package.gif)

### 15. ʹ��DNF�Ƴ����������õ��������Orphan Packages�� ###

��ЩΪ������������װ�����������Ӧ�ĳ���ɾ����㲻����Ҫ�ˡ������ù������������������ɾ����

    # dnf autoremove

![Remove Orphan Packages](http://www.tecmint.com/wp-content/uploads/2015/05/Autoremove-Packages.gif)

### 16. ʹ��DNF�Ƴ����������� ###

������ʹ��dnfʱ�������������ڵ�ͷ���Ͳ��������������ǻᵼ�´������ǿ���ʹ�����������������������Ͱ���Զ�̰���Ϣ��ͷ����

    # dnf clean all

![Remove DNF Cache](http://www.tecmint.com/wp-content/uploads/2015/05/Remove-Cache-Packages.gif)

### 17. ����ض�DNF����İ��� ###

��������Ҫ�ض���DNF����İ��������磬clean��������ͨ��������������õ���

    # dnf help clean

![Get DNF Command Help](http://www.tecmint.com/wp-content/uploads/2015/05/Help-on-DNF-Command.gif)

### 18. �г�����DNF�������ѡ�� ###

Ҫ��ʾ����dnf�������ѡ�ֻ��Ҫ��

    # dnf help

![Get Help on DNF Options](http://www.tecmint.com/wp-content/uploads/2015/05/DNF-Options.gif)

### 19. �鿴DNF����ʷ��¼ ###

�����Ե���'dnf history'���鿴�Ѿ�ִ�й���dnf������б������������֪��ʲô����װ/�Ƴ��Լ�ʱ�����

    # dnf history

![Check DNF History](http://www.tecmint.com/wp-content/uploads/2015/05/Check-DNF-History.gif)

### 20. ��ʾ����������� ###

'dnf grouplist'������Դ�ӡ���п��õĻ��Ѱ�װ������������û��ʲô������������г�������֪��������顣

    # dnf grouplist

![List All Group Packages](http://www.tecmint.com/wp-content/uploads/2015/05/List-All-Group-Packages.gif)

### 21. ʹ��DNF��װһ��������� ###

Ҫ��װһ���������������һ���������飨���磬Educational Softaware����ֻ��Ҫִ�У�

    # dnf groupinstall 'Educational Software'

![Install Group Packages](http://www.tecmint.com/wp-content/uploads/2015/05/Install-Group-Packages.gif)

### 22. ����һ��������� ###

����ͨ�����������������һ��������飨���磬Educational Software����

    # dnf groupupdate 'Educational Software'

![Update Group Package](http://www.tecmint.com/wp-content/uploads/2015/05/Update-Group-Package.gif)

### 23. �Ƴ�һ��������� ###

����ʹ��������������Ƴ�һ��������飨���磬Educational Software����

    # dnf groupremove 'Educational Software'

![Remove Group Package](http://www.tecmint.com/wp-content/uploads/2015/05/Remove-Group-Package.gif)

### 24. ��ĳ���ض��Ĳֿⰲװһ������� ###

DNF���Դ��κ��ض��Ĳֿⰲװһ������������磬phpmyadmin����

    # dnf --enablerepo=epel install phpmyadmin

![Install Package From Specific Repo](http://www.tecmint.com/wp-content/uploads/2015/05/Install-Package-From-Specific-Repo.gif)

### 25. ���Ѱ�װ�������ͬ�����ȶ����а� ###

'dnf distro-sync'��ͬ�������Ѱ�װ������������п����Ĳֿ���������ȶ��汾�����û���������ѡ�����ͬ�������Ѱ�װ���������

    # dnf distro-sync

![Synchronize Packages to Stable Version](http://www.tecmint.com/wp-content/uploads/2015/05/Synchronize-Packages.gif)

### 26. ���°�װһ������� ###

'dnf reinstall nano'������°�װһ���Ѿ���װ������������磬nano����

    # dnf reinstall nano

![ReInstall Package](http://www.tecmint.com/wp-content/uploads/2015/05/Re-Install-Package.gif)

### 27. ����һ������� ###

ѡ��'downgrade'����ʹһ������������磬acpid�����˵��Ͱ汾��

    # dnf downgrade acpid

ʾ�����

    Using metadata from Wed May 20 12:44:59 2015
    No match for available package: acpid-2.0.19-5.el7.x86_64
    Error: Nothing to do.

**�ҵĹ۲�**��dnf���ᰴԤ�����������һ���������������Ϊһ��bug���ύ��

### ���� ###

DNF��YUM���������������Ʒ�����������Զ�������о����Linuxϵͳ����Ա���������Ĺ��������磺

- `--skip-broken`����DNFʶ�𣬲���DNF��û����������
- ���������ܻ�����dnf provides������Ҳû��'resolvedep'�����ˡ�
- û��'deplist'�����������������������
- ���ų�һ���ֿ���ζ�������в������ų��òֿ⣬����yum�У��ų�һ���ֿ�ֻ�ڰ�װ��������ʱ���ų����ǡ�

���Linux�û�����Linux��̬ϵͳ�����������⡣����[Systemd�滻��init system][3]v������DNF���ڲ��ú��滻YUM��������Fedora 22����������RHEL��CentOS��

����ô���أ��ǲ��Ƿ��а������Linux��̬ϵͳ����ע���û������ڳ������û�Ը����㣵ķ���ǰ���أ�IT��ҵ��������һ�仰 - �����û�л���ΪʲôҪ���أ�����System V��YUM��û�л���

���������ƪ���µ�ȫ���ˡ������·������������˽����ı����뷨�����޺ͷ����԰������Ǵ�����лл��

--------------------------------------------------------------------------------

via: http://www.tecmint.com/dnf-commands-for-fedora-rpm-package-management/

���ߣ�[Avishek Kumar][a]
���ߣ�[wwy-hust](https://github.com/wwy-hust)
У�ԣ�[У����ID](https://github.com/У����ID)

������ [LCTT](https://github.com/LCTT/TranslateProject) ԭ�����룬[Linux�й�](https://linux.cn/) �����Ƴ�

[a]:http://www.tecmint.com/author/avishek/
[1]:http://www.tecmint.com/20-linux-yum-yellowdog-updater-modified-commands-for-package-mangement/
[2]:http://www.tecmint.com/dnf-next-generation-package-management-utility-for-linux/
[3]:http://www.tecmint.com/systemd-replaces-init-in-linux/