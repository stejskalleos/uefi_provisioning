# Debian 12

- [Repo](http://http.us.debian.org/debian/dists/bookworm/main/installer-amd64/current/images/netboot/debian-installer/amd64)

## Preparations

```console
cd ./boot/debian_12

# Kernel
wget -O vmlinuz http://http.us.debian.org/debian/dists/bookworm/main/installer-amd64/current/images/netboot/debian-installer/amd64/linux

# InitRAM disk
wget http://http.us.debian.org/debian/dists/bookworm/main/installer-amd64/current/images/netboot/debian-installer/amd64/initrd.gz

# Grub loader
wget http://http.us.debian.org/debian/dists/bookworm/main/installer-amd64/current/images/netboot/debian-installer/amd64/bootnetx64.efi -O grubx64.efi

# This one doesn't work
#wget http://http.us.debian.org/debian/dists/bookworm/main/installer-amd64/current/images/netboot/debian-installer/amd64/grubx64.efi

sudo chown -R $USER: .
```
