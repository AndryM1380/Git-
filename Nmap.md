# Git-
Nmap («Network Mapper») - это утилита с открытым исходным кодом для исследования сети и проверки безопасности. Она была разработана для быстрого сканирования больших сетей, хотя прекрасно справляется и с единичными целями. Nmap использует "сырые" IP пакеты оригинальным способом, чтобы определить какие хосты доступны в сети, какие службы (название приложения и версию) они предлагают, какие операционные системы (и версии ОС) они используют, какие типы пакетных фильтров/брандмауэров используются и еще множество других характеристик. В то время, как Nmap обычно используется для проверки безопасности, многие системные администраторы находят ее полезной для обычных задач, таких как контролирование структуры сети, управление расписаниями запуска служб и учет времени работы хоста или службы.
Выходные данные Nmap это список просканированных целей с дополнительной информацией по каждой из них в зависимости от заданных опций. Ключевой информацией является «таблица важных портов». Эта таблица содержит номер порта, протокол, имя службы и состояние. Состояние может иметь значение open (открыт), filtered (фильтруется), closed (закрыт) или unfiltered (не фильтруется). Открыт означает, что приложение на целевой машине готово для установки соединения/принятия пакетов на этот порт. Фильтруется означает, что брандмауэр, сетевой фильтр, или какая-то другая помеха в сети блокирует порт, и Nmap не может установить открыт этот порт или закрыт. Закрытые порты не связаны ни с каким приложением, но могут быть открыты в любой момент. Порты расцениваются как не фильтрованные, когда они отвечают на запросы Nmap, но Nmap не может определить открыты они или закрыты. Nmap выдает комбинации открыт|фильтруется и закрыт|фильтруется, когда не может определить, какое из этих двух состояний описывает порт. Эта таблица также может предоставлять детали о версии программного обеспечения, если это было запрошено. Когда осуществляется сканирование по IP протоколу (-sO), Nmap предоставляет информацию о поддерживаемых протоколах, а не об открытых портах.
Типичный пример сканирования с помощью Nmap
# nmap 

Starting Nmap ( https://nmap.org )
Interesting ports on scanme.nmap.org (64.13.134.52):
(The 1663 ports scanned but not shown below are in state: filtered)
PORT    STATE  SERVICE VERSION
22/tcp  open   ssh     OpenSSH 3.9p1 (protocol 1.99)
53/tcp  open   domain
70/tcp  closed gopher
80/tcp  open   http    Apache httpd 2.0.52 ((Fedora))
113/tcp closed auth
Device type: general purpose
Running: Linux 2.4.X|2.5.X|2.6.X
OS details: Linux 2.4.7 - 2.6.11, Linux 2.6.0 - 2.6.11

Interesting ports on playground.nmap.org (192.168.0.40):
(The 1659 ports scanned but not shown below are in state: closed)
PORT     STATE SERVICE       VERSION
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn
389/tcp  open  ldap?
445/tcp  open  microsoft-ds  Microsoft Windows XP microsoft-ds
1002/tcp open  windows-icfw?
1025/tcp open  msrpc         Microsoft Windows RPC
1720/tcp open  H.323/Q.931   CompTek AquaGateKeeper
5800/tcp open  vnc-http      RealVNC 4.0 (Resolution 400x250; VNC port: 5900)
5900/tcp open  vnc           VNC (protocol 3.8)
MAC Address: 00:A0:CC:63:85:4B (Lite-on Communications)
Device type: general purpose
Running: Microsoft Windows NT/2K/XP
OS details: Microsoft Windows XP Pro RC1+ through final release
Service Info: OSs: Windows, Windows XP

Nmap finished: 2 IP addresses (2 hosts up) scanned in 88.392 seconds
**1.** Скачал приложение
![image](https://user-images.githubusercontent.com/112687453/192988342-92b4c47a-f183-46e0-bef4-3f678da1edf9.png)
**2.** Открыл приложение 
![image](https://user-images.githubusercontent.com/112687453/192988527-c9fe1b65-4d85-4237-93b1-97caf198ff91.png)
**3.** Ввел цель
![image](https://user-images.githubusercontent.com/112687453/192990264-5e493112-c96c-483a-99cf-1254a38514e8.png)
**4.** Выбрал интенсивное сканирование 
![image](https://user-images.githubusercontent.com/112687453/192990681-187e0ca9-6dee-4d1e-abae-4e61384f00d2.png)
**5.** Просканировал сеть интернет 
![image](https://user-images.githubusercontent.com/112687453/192991116-618b248e-595a-4e64-a63c-f97676cfaa57.png)
![image](https://user-images.githubusercontent.com/112687453/192991171-a63b048e-2460-4caa-bfab-86fab4e0c0b0.png)
![image](https://user-images.githubusercontent.com/112687453/192991290-d12f266c-a611-4ec7-bb2a-ad40215fb62d.png)
![image](https://user-images.githubusercontent.com/112687453/192991385-89482783-b7ec-4291-8f74-065cbdf1634c.png)
![image](https://user-images.githubusercontent.com/112687453/192991496-f4cfb71a-cb82-43bc-b9c3-b21fb50cb8e0.png)

