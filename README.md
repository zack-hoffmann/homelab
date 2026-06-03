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

## TODOs
- [x] Set up DNS on venser
- [x] Clean up DNS/hostnames on all machines
- [x] Finish setting up grist
- [X] Set up local admin accounts on all servers
- [X] Set up OpenLDAP on venser
- [ ] Set up LDAP sssd on grist and sync vaulthome ownership
- [ ] Mount grist storage on other machines
- [ ] Set up all machines to use OpenLDAP for auth
- [ ] Back up vivien, garruk, and gideon to grist
- [ ] Redo garruk as TalosOS kube machine
- [ ] Move Homebridge to garruk (k8s)
- [ ] Move LetsEncrypt to garruk (k8s)
- [ ] Set up SSL share on grist
- [ ] Update OpenLDAP to use SSL share
- [ ] Redo gideon as k8s control plane and worker
- [ ] Add garruk to k8s cluster as worker only
- [ ] Redo vivien as k8s worker