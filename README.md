#### psintroverenvvagrant
#####test drive
######install on ubuntu
```
wget ...
dpkg -i ....
gpg --with-fingerprint oracle_vbox.asc
apt-key add oracle_vbox.asc
```
######display a gui
```
(in ubuntu)
vboxmanage -v
vboxmanage list runningvms
```
######aharing files
save files in folder and see files in guest machine
```
cd /
````
######destroy
```
vboxmanage list vms
```
######windows line endings
create a file ```.gitattributes```
edit
```
* text eol=if
```
or using editorconfig plugin. create ```.editorconfig```
edit
```
root = true
[*]
end_of_line=if
insert_final_newline=true
indent_style=space
indent_size=2
```
######additional help
```
vagrant -h
```
```
vagrant init hashicorp/trusty32 --minimal
```
#####webdev env
######install nginx
edit Vagrantfile
```
config.vm.hostname = "dev"
config.vm.provision "shell",path: "provision.sh"
```
when booting first time using```vagrant up```, it will execute the script, but when using ```vagrant reload```, it will not.  
use ```vagrant provision``` to force running the script

######provisioning
Idempotent: an action produces the same result when run multiple times.

######sharing and version
for nginx, defualt etc:
```
/etc/nginx/sites-enabled/(default)
```
default root
```
root /usr/share/nginx/www
```

we can sync:
```
cp -r /usr/share/nginx/www /vagrant/www
```
to let nginx serve new folder
```
sudo rm -rf /usr/share/nginx/www
sudo ln -s /vagrant/www /usr/share/nginx/www
sudo unlink /usr/share/nginx/www
```
force destroy
```
vagrant destroy -f
```
######vagrant share
register a account in vagreantcloud
```
vagrant login
vagrant share
```
If share using ssh:
```
vagrant share --ssh
```
connect:
```
vagrant connect --ssh name
```
######sharing and versioning nginx onfig file
```
mkdir /vagrant/sites-enabled
cp /etc/nginx/sites-enabled/default /vagrant/sites-enabled
```

change provision.sh
```
sudo rm -rf /etc/nginx/sites-enabled
sudo cp /etc/nginx/sites-enabled/default /vagrant/sites-enabled
```

  
