# README

## Instructions

Install VirtualBox and Vagrant for your platform.

Clone this repo and run

```bash
vagrant up --provider=parallels
```

Reboot the VM.

## Set root user password

Log in using login vagrant (password vagrant) and run

```bash
passwd root
```

## SSH from host

See VM network port forwarding settings to find which port on host is mapped to port 22 (default ssh port) on VM, then run

```bash
ssh -p 2200 root@localhost
```
