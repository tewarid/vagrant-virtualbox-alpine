# README

## Instructions

Install VirtualBox and Vagrant for your platform.

Clone this repo and run

```bash
vagrant up
```

Reboot the VM.

## Set root user password

Log in using login vagrant (password vagrant) and run

```bash
passwd root
```

## VirtualBox shared folders

Create a permanent shared folder in VM settings called `home`, [login as root](#set-root-user-password), and run

```bash
modprobe -a vboxsf
mount -t vboxsf home /mnt/home
```

You can also add the following to `/etc/fstab` so the folder is mounted automatically

```fstab
home            /mnt/home       vboxsf  defaults 0 0
```

## SSH from host

See VM network port forwarding settings to find which port on host is mapped to port 22 (default ssh port) on VM, then run

```bash
ssh -p 2200 root@localhost
```
