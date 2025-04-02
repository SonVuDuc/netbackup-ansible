

There are something that you need to change in order to run successfully in your enviroment

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
