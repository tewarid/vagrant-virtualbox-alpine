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

Create a permanent shared folder in VM settings called `home`, log in as root, and run

```bash
modprobe -a vboxsf
mount -t vboxsf home /mnt/home
```

## SSH from host

See VM network port forwarding settings to find which port on host is mapped to port 22 (SSH) on VM, then run

```bash
ssh -p 2200 root@localhost
```
