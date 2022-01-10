## V2Ray Nginx-based vmess+ws+tls one-click installation script

> Thanks to JetBrains for the non-commercial open source software development license

> Thanks for non-commercial open source development authorization by JetBrains
### About VMess MD5 Certification Information Retirement Mechanism
> From January 1, 2022, the server side will disable compatibility with MD5 authentication information by default. Any client using MD5 authentication will not be able to connect to a server that disables VMess MD5 authentication.

Affected users, we strongly recommend that you reinstall and set alterid to 0 (the default value has been modified to 0 at present), and no longer use the VMess MD5 authentication mechanism
If you don't want to reinstall, you can force compatibility with MD5 authentication by using https://github.com/KukiSa/VMess-fAEAD-disable

### Telegram groups
* telegram exchange group: https://t.me/wulabing_v2ray
* Telegram update announcement channel: https://t.me/wulabing_channel

### Ready to work
* Prepare a domain name and add the A record.
* [V2ray official description](https://www.v2ray.com/), learn about TLS WebSocket and V2ray related information
* Install wget

### How to install/update (h2 and ws versions have been merged)
Vmess+websocket+TLS+Nginx+Website
````
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/wulabing/V2Ray_ws-tls_bash_onekey/master/install.sh" && chmod +x install.sh && bash install .sh
````

VLESS+websocket+TLS+Nginx+Website
````
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/wulabing/V2Ray_ws-tls_bash_onekey/dev/install.sh" && chmod +x install.sh && bash install .sh
````

### Precautions
* If you don't understand the specific meaning of each setting in the script, except the domain name, please use the default value provided by the script
* Use of this script requires you to have Linux foundation and experience, understand some knowledge of computer networks, and basic computer operations
* Currently Debian 9+ / Ubuntu 18.04+ / Centos7+ is supported. Some Centos templates may have intractable compilation problems. It is recommended that if you encounter compilation problems, please change to other system templates
* The group owner only provides extremely limited support, if you have any questions, you can ask group friends
* Every Sunday at 3:00 a.m., Nginx will automatically restart to cooperate with the timing task of issuing the certificate. During this period, the node cannot be connected normally. The estimated duration is several seconds to two minutes.

### Changelog
> Please check CHANGELOG.md for updates

### Thanks
* ~~Another branch version of this script (Use Host) address: https://github.com/dylanbai8/V2Ray_ws-tls_Website_onekey Please choose according to your needs~~ The author may have stopped maintenance
* MTProxy-go TLS version project reference in this script https://github.com/whunt1/onekeymakemtg Thanks to whunt1
* In this script, the original project reference of the Ruisu 4 in 1 script https://www.94ish.me/1635.html Thanks here
* In this script, the modified version of the Ruispeed 4-in-1 script is referenced https://github.com/ylx2016/Linux-NetSpeed ​​Thanks to ylx2016

### Certificate
> If you already have the certificate file for the domain name you are using, you can name the crt and key files as v2ray.crt v2ray.key and put them in the /data directory (if the directory does not exist, please create a directory first), please pay attention to the certificate file permissions and the validity period of the certificate. After the validity period of the custom certificate expires, please renew it by yourself.

The script supports the automatic generation of let's encrypted certificates, which are valid for 3 months. In theory, the automatically generated certificates support automatic renewal.

### View client configuration
`cat ~/v2ray_info.txt`

### Introduction to V2ray

* V2Ray is an excellent open source network proxy tool that can help you experience the Internet smoothly. Currently, all platforms support the use of Windows, Mac, Android, IOS, Linux and other operating systems.
* This script is a one-click complete configuration script. After all processes are running normally, you can set the client directly according to the output results and use it
* Please note: We still strongly recommend that you fully understand the workflow and principles of the entire program

### It is recommended to build only a single proxy for a single server
* This script installs the latest version of V2ray core by default
* The latest version of V2ray core is 4.22.1 (at the same time, please pay attention to the synchronous update of the client core, you need to ensure that the client kernel version >= the server kernel version)
* It is recommended to use the default port 443 as the connection port
* The fake content can be replaced by yourself.

### Precautions
* It is recommended to use this script in a pure environment. If you are a novice, please do not use the Centos system.
* Please do not use this program in a production environment until the script is actually available to try.
* This program relies on Nginx to implement related functions. Please use [LNMP](https://lnmp.org) or other similar Nginx scripts to install Nginx. Users who have installed Nginx should pay special attention. Using this script may cause unpredictable errors (not tested). , if it exists, subsequent versions may address this issue).
* Some functions of V2Ray depend on the system time, please make sure that the system UTC time error of your V2Ray program is within three minutes, regardless of time zone.
* This bash relies on [V2ray official installation script](https://install.direct/go.sh) and [acme.sh](https://github.com/Neilpang/acme.sh) to work.
* For Centos system users, please allow program-related ports in the firewall in advance (default: 80, 443)


### Startup method

Start V2ray: `systemctl start v2ray`

Stop V2ray: `systemctl stop v2ray`

Start Nginx: `systemctl start nginx`

Stop Nginx: `systemctl stop nginx`

### Related directories

Web directory: `/home/wwwroot/3DCEList`

V2ray server configuration: `/etc/v2ray/config.json`

V2ray client configuration: `~/v2ray_info.inf`

Nginx directory: `/etc/nginx`

Certificate files: `/data/v2ray.key and /data/v2ray.crt` Note the certificate authority settings

### Donate

You can use my Bricklayer AFF to buy VPS

https://bandwagonhost.com/aff.php?aff=63939

You can use my justmysocks AFF to buy proxies from bricklayers

https://justmysocks.net/members/aff.php?aff=17621
