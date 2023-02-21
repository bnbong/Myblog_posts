프로젝트에서 웹 백엔드 개발과 서버에 대한 공부를 병행하면서 많은 시행착오를 겪었습니다. 어제도 애용하고 있는 클라우드 서비스인 'Vultr'에서 사용하고 있는 우분투 서버 인스턴스의 더 좋은
하드웨어 스펙을 가지고 있는 플랜으로 업그레이드를 하고 서버에 ssh 접속을 시도했으나 먹히질 않았습니다.

간신히 클라우드 서비스를 통해서 VPS접속으로 내부 인스턴스에 접속을 했고 문제점을 파악한 결과 외부와 통신하는 모든 수단들이 막혀있는걸 확인했습니다.

어째서인지 DNS 설정이 모두 disable이 되어 있고 우분투 기본 방화벽 ufw도 갑자기 사라져 버렸으며 외부와의 접속이 아예 불가능하니 기본적인 ping도 안되는 상황이고 우분투 서버와도 접속이 안되어
apt-get update 명령어도 안먹히는 상황이었습니다.

그나마 iptables가 남아있는 것 같길래 iptables 설정을 만져봤으나 설치되어 있는 iptables 1.8.4버전의 명령어가 최신 버전과 차이가 있는지라 설정 적용도 못했습니다(애초에 iptables.service도 없는 상황이었습니다..)

해당 인스턴스는 Visual Studio Code의 Code-server를 띄워놓은 서버인데 그동안 작업해놓고 커밋을 안해놓은 자료들이 있어서 어떻게든 살려보려고 노력을 했으나 눈물을 머금고 서버를 초기화하기로 결정합니다..

이왕 새로 우분투 서버를 설치한 김에 우분투 서버를 처음 설치하게 되면 설정해야할 요소들에 대해 소개해볼까 합니다. 서버 기초 설정 작업을 하면서 제가 겪었던 시행착오들도 나열되어 있으니 의식의 흐름대로 읽어주시길 바랍니다ㅎ

## 우분투 서버를 처음 설치하고 나서 설정해야 할 요소들

1. root 패스워드 설정: root 계정은 시스템에서 모든 권한을 가지는 계정입니다. 따라서 root 계정의 패스워드를 설정하고, 복잡한 암호를 사용하여 보안을 강화해야 합니다.
2. 방화벽 설정: 우분투에는 기본적으로 UFW(Uncomplicated Firewall) 방화벽이 탑재되어 있습니다. 이를 활성화하고, 필요한 포트만 열어주어 보안을 강화해야 합니다.
3. 업데이트 및 업그레이드: 우분투 서버를 설치한 이후 최신 패키지로 업데이트하고, 시스템을 업그레이드해주어 보안 취약점을 최대한으로 보호해야 합니다.
4. SSH 설정: SSH를 사용하여 원격으로 서버에 접속할 수 있도록 설정하고, 인증키를 사용하여 보안을 강화해야 합니다.
5. 시간대 설정: 올바른 시간대를 설정하여 로그 및 기타 시스템 이벤트를 올바르게 기록할 수 있도록 합니다.

### 우분투 서버 시간대 변경

우분투 서버에서 시간대를 변경하려면, 다음과 같은 단계를 따르면 됩니다.

1. 현재 서버의 시간대 확인

```
$ timedatectl
```

위 명령어를 실행하면 현재 시스템의 시간과 시간대 정보가 출력됩니다.
기본적으로는 UTC로 설정이 되어 있습니다. 저는 서버 시간대를 KST로 설정하고 싶어서 KST시간과 관련된 설정을 추가하기로 했습니다.

2. KST 시간대 추가

```
$ sudo timedatectl set-timezone Asia/Seoul
```

위 명령어를 실행하면 Asia/Seoul 시간대가 추가되고, 서버 시간대가 KST로 변경됩니다.

3. 변경된 시간대 확인

```
$ timedatectl
```

위 명령어를 실행하면 변경된 서버의 시간과 시간대 정보가 출력됩니다.

이제 서버의 시간대가 KST로 설정되었습니다. 주의해야 할 점은, 시스템의 시간대 변경 후 서버의 시간을 확인하고, 필요하다면 동기화를 해주어야 합니다. 서버의 시간이 올바르지 않으면, 로그 기록이나 보안 등에 영향을 줄 수 있기 때문입니다. 동기화는 NTP(Network Time Protocol)를 사용하여 수행할 수 있습니다.

NTP를 사용하면 인터넷을 통해 전 세계의 정확한 시간 정보를 수집하여 서버의 시간을 동기화할 수 있습니다.

저는 NTP 패키지를 설치하고, 설정 파일을 수정하여 NTP 서버를 지정해보기로 했습니다.

1. NTP 패키지 설치

```
$ sudo apt-get update
$ sudo apt-get install ntp
```

2. NTP 설정 파일 수정

```
$ sudo nano /etc/ntp.conf
```

설정 파일을 열어서, NTP 서버를 지정할 수 있는 서버 주소를 추가합니다. 예를 들어, 아래와 같이 지정할 수 있습니다.

```
server 0.asia.pool.ntp.org
server 1.asia.pool.ntp.org
server 2.asia.pool.ntp.org
```

여러 개의 서버를 지정하면, 하나의 서버에서 시간 정보를 받지 못해도 다른 서버에서 시간 정보를 받아서 시간을 동기화할 수 있습니다. 위 설정은 Asia 지역의 NTP 서버를 사용하도록 지정한 것입니다.

1. NTP 서비스 재시작

```
$ sudo systemctl restart ntp
```

NTP 서비스를 재시작하여 설정을 적용합니다.

2. 시간 정보 확인

```
$ sudo ntpq -p
```

위 명령어를 실행하면 현재 서버의 NTP 서버와 동기화된 시간 정보를 확인할 수 있습니다.

ntpq는 ntp의 설정을 도와주는 데몬입니다.

NTP를 사용하여 서버의 시간을 동기화하면, 시간 정보를 수집하기 위해 인터넷에 연결되어 있어야 합니다. 따라서, 서버가 인터넷에 연결되어 있지 않거나, 방화벽 등으로 인해 NTP 패킷이 차단되는 경우에는 동기화가 되지 않을 수 있습니다. 이 경우에는 로컬 네트워크 내에 NTP 서버를 구축하거나, 외부 시간 정보를 수집하여 동기화할 수 있는 다른 방법을 고려해야 합니다.

ntpq -p 명령어를 입력하면 현재 시스템의 NTP(peer) 서버와의 연결 상태를 보여주는 정보를 출력합니다. 아시아 NTP 서버로부터 값을 정상적으로 수신했다면, 해당 서버의 주소와 상태가 출력되어야 합니다. 다음과 같은 출력물이 나와야 합니다.

```
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
*ntp.example.com  123.45.67.89     3 u   64   64    1    0.216   -0.019   0.067
```

여기서 **`remote`** 열은 NTP(peer) 서버의 주소, **`refid`** 열은 해당 서버가 동기화하는 다른 서버의 주소, **`st`** 열은 Stratum 레벨, **`delay`**, **`offset`**, **`jitter`** 열은 각각 시간 동기화 지연 시간, 시스템 시간 차이, 그리고 시간 흔들림을 나타냅니다. **`*`** 표시가 있는 경우 해당 서버가 현재 시스템의 기본 NTP(peer) 서버로 설정되어 있음을 나타냅니다.

NTP서버 또한 외부와의 연결을 해야 하는 서비스라서 방화벽 포트를 열어줘야 합니다. NTP 서버는 기본적으로 123번 포트를 사용하고 있습니다. NTP 서버가 사용하는 포트를 확인하는 방법은 다음과 같습니다.

1. nmap 사용

```
$ sudo nmap -sU -p 123 <ntp-server-ip>
```

1. telnet 사용

```
$ telnet <ntp-server-ip> 123
```

위 명령어에서 **`<ntp-server-ip>`**는 NTP 서버의 IP 주소를 입력하면 됩니다. 만약 NTP 서버가 로컬 머신에서 실행 중이라면 **`127.0.0.1`**로 대체할 수 있습니다.

서버 포트는 ufw를 사용해서 열면 되지만, 만약 서버가 공용 인터넷에 노출되어 있고 NTP 서버가 인터넷에서 가져오는 경우라면, 방화벽 설정 외에도 인터넷 공급자(ISP)가 123번 포트를 차단하고 있는 경우가 많으므로 이를 확인해야 합니다. 이 경우에는 인터넷 공급자(ISP)에게 문의하여 문제를 해결해야 합니다.

여기 까지 설정하면 timedatectl명령어를 입력했을 때 다음과 같은 결과물이 출력됩니다.

```nasm
root@vultrcode-server:~# timedatectl
Local time: Tue 2023-02-21 13:54:45 KST
Universal time: Tue 2023-02-21 04:54:45 UTC
RTC time: Tue 2023-02-2104:54:46
Time zone: Asia/Seoul (KST, +0900)
System clock synchronized: yes
NTP service: n/a
RTC in local TZ: no
```

ntpd를 timedatectl에 적용하려면 timedatectl set-ntp on으로 서비스를 연결해주면 됩니다.

저는 추가로 ntp 말고 systemd-timesyncd 서비스를 사용해서 서버 시간대에 관한 또다른 데몬을 추가해줬는데 다음과 같은 현상이 발생했습니다.

터미널에 timedatectl을 입력할 시:

```nasm
Local time: Tue 2023-02-21 14:10:34 KST
Universal time: Tue 2023-02-21 05:10:34 UTC
RTC time: Tue 2023-02-21 14:10:35
Time zone: Asia/Seoul (KST, +0900)
System clock synchronized: yes
NTP service: active
RTC in local TZ: no
```

터미널에 sudo systemctl status ntp 를 입력해서 ntp 서비스의 동작상태를 확인할 시:

```nasm
● ntp.service
Loaded: masked (Reason: Unit ntp.service is masked.)
Active: inactive (dead) since Tue 2023-02-21 14:09:21 KST; 19s ago
Main PID: 910 (code=exited, status=0/SUCCESS)
Feb 21 14:09:21 vultrcode-server ntpd[910]: 121.162.54.1 local addr 158.247.209.206 -> <null>
Feb 21 14:09:21 vultrcode-server ntpd[910]: 106.247.248.106 local addr 158.247.209.206 -> <null>
Feb 21 14:09:21 vultrcode-server ntpd[910]: 2406:da12:b86:2c32:3045:8e6c:779c:7e0b local addr 2401:c080:1c01:b19:5400:3ff:fee8:12a5 -> <>
Feb 21 14:09:21 vultrcode-server ntpd[910]: 2001:678:8::123 local addr 2401:c080:1c01:b19:5400:3ff:fee8:12a5 -> <null>
Feb 21 14:09:21 vultrcode-server ntpd[910]: 2620:2d:4000:1::41 local addr 2401:c080:1c01:b19:5400:3ff:fee8:12a5 -> <null>
Feb 21 14:09:21 vultrcode-server ntpd[910]: 162.159.200.1 local addr 158.247.209.206 -> <null>
Feb 21 14:09:21 vultrcode-server ntpd[910]: 2620:2d:4000:1::40 local addr 2401:c080:1c01:b19:5400:3ff:fee8:12a5 -> <null>
Feb 21 14:09:21 vultrcode-server ntpd[910]: 116.91.118.97 local addr 158.247.209.206 -> <null>
Feb 21 14:09:21 vultrcode-server systemd[1]: ntp.service: Succeeded.
Feb 21 14:09:21 vultrcode-server systemd[1]: Stopped Network Time Service.
```

저는 처음에 잘만 깔아서 설정해줬던 ntpd 서비스가 갑자기 다운돼서 문제가 있는 줄 알았으나 이렇게 나오는 것이 문제가 되는 것은 아닙니다.

**`systemd-timesyncd`**가 설치되면서 뜨는 설치 로그 중에는 설치 마법사가 알아서 **`ntpd`**를 삭제하는 것을 보실 수 있습니다.

**`systemd-timesyncd`**는 시스템 클라이언트로서 내부적으로 NTP 클라이언트 기능을 수행합니다. 그러므로 **`timedatectl`**에서 "NTP service: active"가 표시된 것은 정상적인 동작입니다.

하지만 **`ntpd`** 와 **`systemd-timesyncd`**와는 별개의 NTP 서비스입니다. **`systemctl status ntp`**명령어는 **`ntpd`**나 **`chronyd`**와 같은 별도의 NTP 데몬을 사용할 경우 해당 서비스 상태를 확인하는 데 사용됩니다.

따라서 **`systemctl status ntp`** 명령어가 **`ntpd`** 또는 **`chronyd`** 데몬을 사용하지 않는 경우 오류가 발생할 수 있습니다.

만약 **`systemd-timesyncd`**가 설치된 경우, 추가적인 NTP 서비스를 실행할 필요가 없습니다. 설정에 문제가 있는건 아니었습니다.

**`timedatectl timesync-status`**명령어를 확인해서 추가적으로 얻어오는 NTP서버의 주기를 확인할 수 있습니다.

```nasm
Server: 2001:19f0:200:144b::1000 ([1.time.constant.com](http://1.time.constant.com/))
Poll interval: 2min 8s (min: 32s; max 34min 8s)
Leap: normal
Version: 4
Stratum: 2
Reference: 81060F1C
Precision: 1us (-23)
Root distance: 18.561ms (max: 5s)
Offset: +9.618ms
Delay: 189.130ms
Jitter: 3.635ms
Packet count: 2
Frequency: +8.934ppm
```

한 시스템에 두 개 이상의 시간 동기화 데몬이 실행되면 서버 시간이 널뛰기 할 수 있습니다.

참고로 [systemd-timesyncd](https://github.com/systemd/systemd/blob/v213/NEWS#L5) 는 SNTP 구현체로 NTP 클라이언트 역할만 합니다. 2020 년 현재 NTP 구현체 중 chrony 쓰는게 가장 좋다고 합니다.

systemd-timesyncd는 NTP가 아니라 SNTP 클라이언트라서 slewing, leap smearing 같은 명령어가 안먹힌다고 합니다.

### root 계정 비밀번호 변경

root 계정에 접속한 뒤, passwd명령어를 입력해서 비밀번호를 변경합니다.

```nasm
# passwd
Changing password for root.
New password:
Retype new password:
passwd: password updated successfully
```

### 우분투 서버의 패키지를 최신으로 업데이트하고 시스템을 업그레이드하는 방법

1. 패키지 리스트 업데이트: **`sudo apt-get update`**
2. 업그레이드 가능한 패키지 확인: **`sudo apt-get upgrade`**
3. 업그레이드 실행: **`sudo apt-get dist-upgrade`**

위 명령어를 차례로 실행하면 패키지를 최신 버전으로 업데이트하고, 시스템을 업그레이드할 수 있습니다. 패키지 업데이트를 실행할 때는 인터넷에 연결되어 있어야 합니다. 업데이트나 업그레이드를 실행할 때는 관리자 권한으로 실행해야 합니다. 따라서 위 명령어 앞에 **`sudo`**를 붙여 실행합니다.

이를 끝으로 기본적인 우분투 설정을 마쳤습니다. 조금 더 공부해서 앞으로는 이번과 같은 참사가 나지 않길 기도해야겠습니다 ㅠㅠ
