# Hoffmann Family Home Lab

## About
**Domain:** the-hoffmanns.org  
**Home Network** IP: 52.144.113.103

## Hosts
| Hostname | Internal IP   | Services                 | Hardware       |
|----------|---------------|--------------------------|----------------|
| gideon   | 192.168.4.137 | DNS, Homebridge, Nginx   |                |
| grist    | 192.168.4.139 | Storage (openmediavault) |                |
| ajani    | 192.168.4.140 | Lucas's personal server  |                |
| vivien   | 192.168.4.156 | Minecraft, Palworld      |                |
| garruk   | 192.168.4.185 | Wumpus Development       |                |
| venser   |               | DNS                      | Libre v2       |

## TODOs
- [ ] Set up DNS on Libre
- [x] Finish setting up grist
- [ ] Mount grist storage on other machines
- [ ] Back up vivien, garruk, and gideon to grist
- [ ] Redo garruk as TalosOS kube machine
- [ ] Move Homebridge to garruk (k8s)
- [ ] Move LetsEncrypt to garruk (k8s)
- [ ] Redo gideon as k8s control plane and worker
- [ ] Add garruk to k8s cluster as worker only
- [ ] Redo vivien as k8s worker