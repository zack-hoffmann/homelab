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
- [ ] Clean up DNS/hostnames on all machines
- [x] Finish setting up grist
- [ ] Mount grist storage on other machines
- [ ] Back up vivien, garruk, and gideon to grist
- [ ] Redo garruk as TalosOS kube machine
- [ ] Move Homebridge to garruk (k8s)
- [ ] Move LetsEncrypt to garruk (k8s)
- [ ] Redo gideon as k8s control plane and worker
- [ ] Add garruk to k8s cluster as worker only
- [ ] Redo vivien as k8s worker