<p align="center">
    <img src="https://github.com/degete/openwrt-conf/blob/main/openwrt.png?raw=true" height="200px"/>
</p>

## **OpenWrt Firmware (X-WRT) for Xiaomi Mi Router 3 (R3)**

### Information

`Router`: [Xiaomi Mi Router 3 (R3)](https://www.mi.com/miwifi3)

`Firmare`: [X-WRT](https://x-wrt.com/)

### Ansible Playbooks

There are different playbooks which groups different roles:

- `sysupgrade`: updates the firmware to the latest version available on the website.
  - Remember to enable SSH and root authentication after factory reset

<p align="center">
    <img src="https://github.com/degete/openwrt-conf/blob/main/ssh.png?raw=true" height="200px"/>
</p>

- `openwrt`
  - `base`: install the main packages such as curl, wget, htop...
  - `adblock`: install adblock package (optional, uncomment)

### Requirements

```
ansible-galaxy collection install -r requirements.yaml
```

### Config

Before running the [openwrt playbook](./openwrt.yaml), please set the variables such as SSID's and SSID Key's. 

### Apply playbook

> If using **ssh password** for logging in (might need to use [sshpass](#sshpass))
```
ansible-playbook -i hosts.yaml openwrt.yaml --user=root -k
```

>If using **ssh key** on the known-hosts
```
ansible-playbook -i hosts.yaml openwrt.yaml --user=root -K
```

### Troubleshoots

#### ssshpass

https://sourceforge.net/projects/sshpass/files/sshpass/

```
./configure
make install
```