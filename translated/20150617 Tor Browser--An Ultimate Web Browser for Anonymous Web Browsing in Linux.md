Tor�������Linux����������Web������ռ������
================================================================================
���Ǵ�����˶����������滨�Ѻܶ�ʱ�䡣��������ʹ�õ�Ӧ�ó�����Ҫ���������һ��Web������������������������ĻҪ�Կͻ���/�������ķ�ʽ��¼��������̻����IP��ַ��������Ϣ����������Լ����Ǳ�ڵ���Ϣ����Щ��Ϣ�����������ʽ������ʹ�ã������Ǳ�ڵ�Σ���ԡ�

![��Linux�а�װTor�����](http://www.tecmint.com/wp-content/uploads/2014/04/Install-tor-browser-in-linux.jpg)

Tor����������������

���⣬���Ұ�ȫ�֣�NSA�������ʼ���������¼���ǵ������㼣��������˵ĳ�����޵Ĵ��������Ҳ�ᱻ������Ϊ�����Ѽ����������������ҵ�͹�˾�������������ʴ����������

��ˣ�������Ҫ�������һ��С�͡���������Я����Ӧ�ó������ܴﵽ������Ч����Tor���������������һ��Ӧ�ã���ӵ��������ᵽ�����й��ܣ�������ֹ�ڴˡ�

��ƪ���������ǻ�����Tor����������Ĺ��ܣ�����ʹ�÷�ʽ�����򣬰�װ�Լ���������Tor���������Ҫ���档

#### ʲô��Tor������� ####

Tor��һ�����ɷַ���Ӧ���������BSDʽ�����֤������ͨ���䰲ȫ�ɿ������ʽ�Ľṹ�������û������Ľ��������������ǰ���������Ľṹ���������ƣ�Tor����Ϊ�����·�����������Ӧ������C����д�ɵġ�

#### Tor������Ĺ��� ####

- ��ƽ̨���á����磬���Ӧ�ó�����Linux��Windows��Mac�¶����á�
- �ڷ������ݵ�������ǰ���и��ӵ����ݼ��ܡ�
- �ڿͻ��˽��е������Զ����ܡ�
- ���ǻ���������Tor���̵Ľ�ϡ�
- �Է���������վ�ṩ�����ԡ�
- ���Է�����������վ��
- ���豩¶ԴIP�����ִ������
- �����ڷ���ǽ������·����/�����صķ����Ӧ�ó���
- ��Я�� - ����ֱ�Ӵ�USB�洢������һ��Ԥ���õ�web����������豾�ذ�װ��
- ��x86��x86_64ƽ̨����
- ����ͨ��ʹ��Tor�ԡ�socks4a���ķ�ʽ�ڡ�localhost���ġ�9050���˿������ô���������FTP��
- Torӵ�д�����ǧ��ת�����ϰ����û���������

#### Tor�������ι����� ####

Tor�Ĺ�����ʽ�������·�ɵĸ�����·�ɵĽṹ������У�����ÿһ�㶼Ƕ������һ�����棬�������һ��������Ƕ�׵Ľṹ�����μ������ݲ�����ͨ�������·���з��͡��ڿͻ���һ��ÿһ�㶼�ڽ������ݵ���һ��֮ǰ�������ݡ����һ���ڽ�ԭʼ���ݴ��ݵ�Ŀ�ĵ�ǰ����������һ��ļ������ݡ�

�������������ֽ������в�Ĺ�����Ƶ���˴����������޷�׷��IP�Լ��û��ĵ���λ�ã���˿��������κ��˹۲�������վ����������ӡ�

������Щ���̿�������Щ���ӣ����û�ʹ��Tor�����ʱû�б�Ҫ���ġ�ʵ���ϣ�Tor������Ĺ��������������һ����������Mozilla��Firefox����

### ��Linux�а�װTor����� ###

�����������۵�һ����Tor�������Linux��Windows�Լ�Mac�¶����á��û���Ҫ����ϵͳ�ͼܹ��Ĳ�ͬ����������Ӵ��������µİ汾�����磬Tor�����4.0.4����

- [https://www.torproject.org/download/download-easy.html.en][1]

������Tor�������������Ҫ��װ�������õ������ǲ���Ҫ��װ��Tor��������ֱ�Ӵ������豸�����У����Ҹ���������Ա�Ԥ���á�����ζ�Ų�������е����Կ�����������ֲ��

���ش���ļ���*.tar.xz����������Ҫ��ѹ����

**32λϵͳ**

    $ wget https://www.torproject.org/dist/torbrowser/4.0.4/tor-browser-linux32-4.0.4_en-US.tar.xz
    $ tar xpvf tor-browser-linux32-4.0.4_en-US.tar.xz

**64λϵͳ**

    $ wget https://www.torproject.org/dist/torbrowser/4.0.4/tor-browser-linux64-4.0.4_en-US.tar.xz
    $ tar -xpvf tor-browser-linux64-4.0.4_en-US.tar.xz 

**ע��** : ������������У�����ʹ�á�$����ζ�����ѹ����Ӧ����ͨ�û�������root�û�����ѹ������ǿ�ҽ�������Ҫ��root�û���ѹ������Tor�������

�ڳɹ��Ľ�ѹ�����Ǳ���Խ���ѹ���������ƶ����κεط�/USB�洢�豸�С����ӽ�ѹ���ļ����Է�root�û�ֱ�����С�start-tor-browser����

    $ cd tor-browser_en-US
    $ ./start-tor-browser

![��ʼʹ��Tor�����](http://www.tecmint.com/wp-content/uploads/2014/04/Starting-Tor-Network.jpg)

��ʼʹ��Tor�����

**1. �������ӵ�Tor���硣��������ӡ�֮��Tor���������ð�����ʣ�µ����顣**

![���ӵ�Tor����](http://www.tecmint.com/wp-content/uploads/2014/04/Tor-Network-Settings.jpg)

���ӵ�Tor����

**2. ��ӭ����/��ǩ��**

![Tor��ӭ����](http://www.tecmint.com/wp-content/uploads/2014/04/Tor-Welcome-Screen.png)

Tor��ӭ����

**3. Tor�������Youtube��������Ƶ��**

![��Youtube�Ͽ���Ƶ](http://www.tecmint.com/wp-content/uploads/2014/04/Watching-Video-on-Youtube.jpg)

��Youtube�Ͽ���Ƶ

**4. ��������ַ�Խ������߹���ͽ��ס�**

![�������վ��](http://www.tecmint.com/wp-content/uploads/2014/04/Browsing-Site.jpg)

�������վ��

**5. �������ʾ�ҵ�ǰ�Ĵ���IP��ע���ı�Ϊ��Proxy Server detected����**

![���IP��ַ](http://www.tecmint.com/wp-content/uploads/2014/04/Checking-IP-Address.jpg)

���IP��ַ

**ע��**: ÿ����������Torʱ������Ҫʹ���ı�ģʽ��ָ��Tor�����ű������Ҹ��ն���������Torʱ���������æµ״̬����ο˷���Щ��������һ������/Dock��ͼ���أ�

6. ������Ҫ�ڽ�ѹ���ļ����д���`tor.desktop`��

$ touch tor.desktop

����ʹ����ϲ���ı༭���༭����ļ�������������ı���������ʹ��nano��

    $ nano tor.desktop 

----------

    #!/usr/bin/env xdg-open
    [Desktop Entry]
    Encoding=UTF-8
    Name=Tor
    Comment=Anonymous Browse
    Type=Application
    Terminal=false
    Exec=/home/avi/Downloads/tor-browser_en-US/start-tor-browser
    Icon=/home/avi/Downloads/tor-browser_en-US/Browser/browser/icons/mozicon128.png
    StartupNotify=true
    Categories=Network;WebBrowser;

**ע��**: ȷ���������tor�������·���滻Ϊ���Ļ����е�·����

**7. һ���㶨�����Ϳ���˫��`tor.desktop`�ļ�������Tor������ˣ���������Ҫ�ڵ�һ������ʱ���θ��ļ���**

![TorӦ��������](http://www.tecmint.com/wp-content/uploads/2014/04/Tor-Application-Launcher.jpg)

TorӦ��������

**8. һ����ѡ�������Σ���ע��`tor.desktop`�ļ���ͼ�����ı䡣**

![Torͼ���Ѹı�](http://www.tecmint.com/wp-content/uploads/2014/04/Tor-icon-changed.jpg)

Torͼ���Ѹı�

**9. ��������ק`tor.desktop`��ͼ�����������Dock���д�����ݷ�ʽ��**

![���������Tor��ݷ�ʽ](http://www.tecmint.com/wp-content/uploads/2014/04/Add-Tor-Shortcut-on-Desktop.jpg)

���������Tor��ݷ�ʽ

**10. ����Tor�������**

![����Tor�����](http://www.tecmint.com/wp-content/uploads/2014/04/About-Tor-Browser.jpg)

����Tor�����

**ע��**: �������ʹ�þɰ汾��Tor�������Դ�����Ĵ��ڸ�������

#### Ӧ�õĿ����Ժ����� ####

- ����ʹ�����硣
- ������赲��ҳ�档
- ��������Ӧ�ã�����FTP������֤���簲ȫ�ķ��ʡ�

