# NETBACKUP ANSIBLE FOR AUTOMATION INSTALL AGENT

## This project installs NetBackup Client using Ansible (This version only works on RHEL 7 + Oracle Linux 7).

Make sure to update the following values to run successfully in your environment:

### 1. The NBInstallAnswer.conf file is required for install Netbackup, you need to modify it first
```
ACCEPT_EULA=yes
MACHINE_ROLE=CLIENT
CLIENT_NAME={{ ansible_hostname }}
INSTALL_PATH=/usr
SERVICES=yes
SERVER=<Master Server Name>
MEDIA_SERVER=<Media Server Name, if you have more than 1 Media Server, just add one more line MEDIA_SERVER=>
AUTHORIZATION_TOKEN=<Generated Token from Netbackup Master>
CA_CERTIFICATE_FINGERPRINT=<SHA-256 from Netbackup Master>
INCLUDE_JAVA_GUI_AND_JRE=EXCLUDE
```

### 2. Edit your inventory file

Add clients you would like to install in sector [netbackup-client]

```
[netbackup-all]
nbu-client-02.svlab.com ansible_user=ansible ansible_ssh_private_key_file=~/.ssh/id_rsa
cam-nbu-master
cam-nbu-media

[netbackup-client]
nbu-client-02.svlab.com ansible_user=ansible ansible_ssh_private_key_file=~/.ssh/id_rsa
```

netbackup-ansible/roles/update_hosts/vars/main.yml

```
host_entries:
  - "10.1.29.87 cam-nbu-master"
  - "10.1.29.88 cam-nbu-media"
```

### 3.Make sure to change these NFS values:

I use NFS server to export Netbackup agent installer to all client, so you need to build your own NFS server. 

```
nfs_server: 10.1.29.161
nfs_share: /nfs-share
mount_point: /mnt/netbackup
```



