# smartctl-zabbix

Template and script for monitoring HDD S.M.A.R.T data from Zabbix on Linux OS
S.M.A.R.T. items description copied from Wikipedia (https://en.wikipedia.org/wiki/S.M.A.R.T.)


Arch Linux package
------------------

```
$ cd archlinux
$ makepkg -s
```

This template uses active checks, so you'll need to make some changes
to `/etc/zabbix/zabbix_agentd.conf`. Edit them to match your configuration:

```
# Include=/usr/local/etc/zabbix_agentd.userparams.conf
# Include=/usr/local/etc/zabbix_agentd.conf.d/
Include=/etc/zabbix/zabbix_agentd.conf.d/
# Include=/usr/local/etc/zabbix_agentd.conf.d/*.conf
...
Server=192.168.10.39,192.168.10.17
...
ServerActive=192.168.10.39
...
Hostname=Saturn
```


Manual Installation
-------------------

Install smartctl:
      sudo apt install smartmontools zabbix-sender

Copy the scripts, zabbix_agentd.conf.d into /etc/zabbix/

Copy sudoers.d into /etc/

Check arguments: Server, Hostname, ListenIP in zabbix_agentd.conf

Finally in zabbix setup the discovery rule and related items you need.
