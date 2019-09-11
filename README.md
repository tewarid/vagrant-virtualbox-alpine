# README

## Instructions

Install Parallels, Vagrant, and [Vagrant Parallels Provider](https://github.com/Parallels/vagrant-parallels) for macOS.

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
ssh -p 22 root@localhost
```

## Mount shared folder using CIFS

If you've enabled file sharing using SMB on macOS or Windows, you can mount the shared folder using cifs

```bash
apk add cifs-utils
mount -t cifs //10.211.55.2/<shared folder> /mnt/<shared folder> -o uid=0,gid=0,user=<username>,password=<password>
```

You can also add an entry to `/etc/fstab` to automatically mount folder

```fstab
//10.211.55.2/<shared folder> /mnt/<shared folder> cifs auto,uid=0,gid=0,user=<username>,password=<password> 0 0
```
