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
