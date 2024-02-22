# UEFI provisioning with Libvirt

(Tested on Fedora 39)

## Preconditions

Required packages

```console
dnf install @virtualization dnf-plugins-core
dnf config-manager --add-repo http://www.kraxel.org/repos/firmware.repo
dnf install edk2.git-ovmf-x64
```

Enable Libvirt

```console
systemctl start libvirtd
systemctl enable libvirtd
```

## Libvirt network

Configure network same way as in `data/libvirt_network.xml`

```console
virsh net-edit default
```

Apply the changes

```console
virsh net-destroy default; virsh net-start default
```

## HTTP server

Run the HTTP server FROM the OS directory

```console
python3 -m http.server --protocol HTTP/1.1
```

## Spin up the VM

```console
virt-install  --name="efi_vm"\
  --ram 4096 \
  --vcpus 2 \
  --connect qemu:///system \
  --network network=default,mac=00:AA:BB:CC:25:75 \
  --os-variant debian12 \
  --pxe \
  --boot uefi,loader_ro=yes,loader_type=pflash,nvram_template=/usr/share/edk2/ovmf/OVMF_VARS.fd,loader_secure=no \
  --noreboot
```
