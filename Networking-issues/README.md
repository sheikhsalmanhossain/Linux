
# when i try ping google.com
it shows "temporary failure in name resolution"

#Delete everything Try again:

[## installing time installing kernel failed:
(installing time go to shell terminal: Ctrl+Alt+F2)
## Issue solved: it has a mirror/network setup step, and that’s where the issue comes in. so make internet off during installing.]

# CAN NOT PING GOOGLE.COM SOLVED:

1) Check your netplan config:
ls /etc/netplan/

2) you will see a yaml file ( example abc.yaml)

3)Edit it:
sudo vim /etc/netplan/abc.yaml

4) Replace contents with this (for DHCP + NAT):
network:
  version: 2
  ethernets:
    ens33:
      dhcp4: true

5) Apply changes:
sudo netplan apply

6) ping -c 3 google.com
## BOOM IT WORKS

(2 sept 2025 to 07 sept 2025)
