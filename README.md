# NetBackup Ansible

This project installs NetBackup Client using Ansible.  
Make sure to update the following values:There are some values you need to update to run successfully in your environment:


The NBAnswser is required for install Netbackup 
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
