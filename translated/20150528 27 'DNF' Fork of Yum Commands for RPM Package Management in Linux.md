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

![Check DNF Version](http://www.tecmint.com/wp-content/uploads/2015/05/Check-DNF-Version.gif)

### 2. �г�������DNF�ֿ� ###

dnf�����е�'repolist'ѡ���ʾ��ϵͳ�����п����Ĳֿ⡣

    # dnf repolist

![Check All Enabled Repositories](http://www.tecmint.com/wp-content/uploads/2015/05/Check-All-Enabled-Repositories.gif)

### 3. �г����п����͹رյ�DNF�ֿ� ###

'repolist all'ѡ���ʾ��ϵͳ�����п���/�رյĲֿ⡣

    # dnf repolist all

![List All Enabled/Disabled Repositories](http://www.tecmint.com/wp-content/uploads/2015/05/Check-All-Repositories.gif)

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

### 17. Get Help on Specific DNF Command ###
