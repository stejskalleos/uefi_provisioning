# CentOS 9 provisioning

```console
cd boot/centos_9

# InitRAM disk
wget http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/images/pxeboot/initrd.img

# Kernel
wget http://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/images/pxeboot/vmlinuz

# Grub loader
wget https://mirror.stream.centos.org/9-stream/BaseOS/x86_64/os/EFI/BOOT/grubx64.efi

sudo chown -R $USER: .
```

Getting Shim

- Spin up CentOS 9 Stream machine
- Update all the packages
- Get the Shim from the machine

```console

```

(optional) Validate `ks.cfg`

```console
ksvalidator boot/centos_9/ks.cfg
```

## Run the VM
