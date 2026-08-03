# Venser

## Setup

### Software
* [Libre Computer Flash Tool](https://github.com/libre-computer-project/libretech-flash-tool)
* [Debian](https://distro.libre.computer/ci/debian/12/)

### Steps
1. Unmount and wipe the microSD card if needed
```bash
sudo umount /dev/sdf*
sudo wipefs -a /dev/sdf
```
2. Use flash tool (lft.sh) to flash bootloader to microSD card
```bash
sudo ./lft.sh bl-flash aml-s905x-cc-v2 sdf
```
3. Write the raw, unzipped image 
```bash
sudo dd if=debian-12-base-arm64+aml-s905x-cc.img of=/dev/sdf bs=4M status=progress conv=fsync
```
4. Log in with root (default password "root")
5. Create a non-root user with sudo
```bash
adduser zack
adduser zack sudo
```
6. Enable ssh
```bash
sudo apt update
sudo apt install openssh-server
sudo systemctl enable --now ssh
```

###
ldap_uri = ldaps://ldap.the-hoffmanns.org:636
ldap_search_base = dc=the-hoffmanns,dc=org
ldap_user_search_base = ou=People,dc=the-hoffmanns,dc=org
ldap_group_search_base = ou=Groups,dc=the-hoffmanns,dc=org