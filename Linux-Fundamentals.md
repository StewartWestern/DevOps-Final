# Linux Fundamentals

```ls``` will list the contents of a directory

```ls -la``` will show more details

```vi filename.txt``` will open the vi editor
1. ```vi``` will enter insert mode to edit the file
2. the ESC key will exit
3. ```:wq``` enters command mode that writes and quits
4. ```:q!``` forest vi to quit without saving

```mkdir folder-name-goes-here``` will create a new folder

```mkdir newfolder/subfolder``` will create a subfolder

```mkdir -p newfolder/subfolder``` to create both at once

```sudo dnf -y install tree``` can be installed for better visibility of files

```cp original-file.txt new_file.txt``` can be used to copy a file to a new location. the ```mv``` command can move files.

files and folders can be deleted with 
```
rm filename
rm -d foldername
rm -rf folder
```
rm -rf folder will delete the folder and all contents.
**DO NOT EVER** use sudo rm -rf

## User Management

The following commands create a user associate a user with a name and edit the password of the user
```
sudo adduser {username}
sudo useradd johnSmt -c "John Smith"
sudo passwd johnsmt 
```
will create a group called admins and add a user to that group
```
sudo groupadd admins
sudo usermod johnSmt -aG admins
```

## Networking Basics and Software installation

Will download files to a linux machine
```
wget {url}
```
Package managemnet systems are used with ```apt``` on Ubuntu and ```yum/dnf``` on Red Hat

```sudo dnf update``` updates the list of packages available to install

```sudo dnf upgrade``` will upgrade any out of date software

Most software that runs a service needs to be started with ```sudo systemctl enable {software name}```

```sudo systemctl status {software name}``` to check if it is running