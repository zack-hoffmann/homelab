# Hoffmann Family Home Lab

## About
**Domain:** the-hoffmanns.org  
**Home Network** IP: 52.144.113.103

## Hosts
| Hostname | Internal IP   | Services            | OS             | Hardware       |
|----------|---------------|---------------------|----------------|----------------|
| gideon   | 192.168.4.137 | Homebridge, Nginx   | Ubuntu Server  |                |
| grist    | 192.168.4.139 | Storage             | OpenMediaVault |                |
| ajani    | 192.168.4.140 | Lucas's server      | Ubuntu Server  |                |
| vivien   | 192.168.4.156 | Minecraft, Palworld | Ubuntu Server  |                |
| garruk   | 192.168.4.185 | Wumpus Development  | Ubuntu Server  |                |
| venser   | 192.168.4.54  | DNS                 | Debian         | Libre v2       |

## Instructions
### Joining to Domain
1. Make sure the following are installed: sssd sssd-tools libnss-sss libpam-sss
2. Create /etc/sssd/sssd.conf (see repo copy)
3. chmod 600 /etc/sssd/sssd.conf
4. systemctl enable sssd
5. systemctl start sssd
6. Grant sudo to any necessary users: sudo usermod -a -G sudo zack

## TODOs
- [x] Set up DNS on venser
- [x] Clean up DNS/hostnames on all machines
- [x] Finish setting up grist
- [X] Set up local admin accounts on all servers
- [X] Set up OpenLDAP on venser
- [X] Set up LDAP sssd on grist and sync vaulthome ownership
- [X] Mount grist storage on other machines
- [X] Set up all machines (excl. ajani) to use OpenLDAP for auth
- [X] Back up garruk to grist
- [X] Redo garruk as kube machine
- [X] Set up dummy webapp on garruk
- [X] Port forward 80 and 443 to garruk, confirm dummy webapp ingress
- [X] Move LetsEncrypt to garruk (k8s)
- [X] Set up SSL share on grist
- [X] Move Homebridge to garruk (k8s)
- [X] Move Jellyfin videos to grist
- [X] Move Jellyfin to garruk (k8s)
- [X] Set up SSL certificate share
- [ ] Update OpenLDAP to use SSL share
- [ ] Back up gideon to grist
- [ ] Redo gideon as k8s control plane and worker
- [ ] Add garruk to k8s cluster as worker only
- [ ] Back up vivien to grist
- [ ] Redo vivien as k8s worker