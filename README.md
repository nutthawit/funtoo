# funtoo

## Create VM on VirtualBox
#### 1. First step is create virtual machine on VirtualBox with specs.
```yaml
CPU: '8 core'
RAM: '10 GiB'
HDD: '50 GiB (Dynamically allocated)'
NIC: 'Bridged Adapter'
Enable_EFI_special-OSes-only: True
VideoMemory: '128 MB'
Graphics_Controller: 'VMSVGA'
Enable_3D_Acceleration: True
.
.
.
The rest is left as default.
```
#### 2. Second download [Funtoo](https://build.funtoo.org/livecd/funtoo-livecd-area31-5.1-beta-r1.iso "Area31 Funtoo LiveCD (1.5GB download)") images and used it's as a boot CD.

#### 3. Now following the instruction from [Funtoo Installation Guide](https://www.funtoo.org/Install/Introduction "Install Guide: Introduction").

Used follow pattern for partitions design.
```yaml
/dev/sda1: 
    type: fat32 
    size: 500
    size_unit: MiB
/dev/sda2: 
    type: swap 
    size: 7.5 
    size_unit: GiB
/dev/sda3: 
    type: ext4 
    size: 'used the rest of disk.'
```

For profiles config.
```yaml
arch: x86-64bit
build: current
subarch: intel64-skylake
flovor: workstation
mix-ins: (non set)
```

For VGA support.
```bash
echo "VIDEO_CARD="virtualbox" >> /etc/make.conf
```