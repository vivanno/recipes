# draft Greenbone Vulnerability Manager (Old OpenVAS)

Here is a list of commands to install GVM on Kali Linux 2021. 

 sudo apt update && apt upgrade 

 sudo apt install gvm

 sudo runuser -u _gvm -- gvm-manage-certs -a -f

 sudo runuser -u _gvm -- gvmd --user=admin --new-password=123456789

 sudo runuser -u _gvm -- gvmd –create-user=<UserName> –password=<Password>

 sudo systemctl enable redis-server@openvas.service
 
 sudo systemctl start redis-server@openvas.service

 sudo runuser -u _gvm -- greenbone-nvt-sync
 
 sudo runuser -u _gvm -- greenbone-feed-sync --type SCAP
 
 sudo runuser -u _gvm -- greenbone-feed-sync --type CERT
 
 sudo runuser -u postgres -- /usr/share/gvm/create-postgresql-database

# Verifying the setup

sudo gvm-check-setup 

# Starting the setup

 sudo gvm-setup

 sudo gvm-feed-update
 
 sudo runuser -u _gvm -- greenbone-nvt-sync
 
 sudo runuser -u _gvm -- greenbone-scapdata-sync
 
 sudo runuser -u _gvm -- greenbone-nvt-sync

 (optional) sudo systemctl enable /lib/systemd/system/greenbone-security-assistant.service

 sudo gvm-start

Now you are able to access the admin page using: https://127.0.0.1:9332
  
# create change the user password

 sudo runuser -u _gvm -- gvmd --get-users --verbose
 
 sudo runuser -u _gvm -- gvmd –create-user=vivanno –password=blabla
  
# Failed to find config ‘daba56c8-73ec-11df-a475-002264764cea’g 

 sudo runuser -u _gvm -- gvmd --get-users --verbose
 
 sudo runuser -u _gvm -- gvmd --get-scanners
 
 sudo runuser -u _gvm -- gvmd --modify-setting 08b69003-5fc2-4037-a479-93b440211c73 --value 68988e70-bae3-4033-b576-8022df146863
 
 sudo runuser -u _gvm -- gvmd --modify-scanner 08b69003-5fc2-4037-a479-93b440211c73 --scanner-host=/run/ospd/ospd.sock
