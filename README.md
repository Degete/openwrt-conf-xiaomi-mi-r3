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
- `openwrt`
  - `base`: install the main packages such as curl, wget, htop...
  - `adblock`: install adblock package

### Requirements

```
ansible-galaxy collection install -r requirements.yml
```

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