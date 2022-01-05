# Linux-Win

################################LINUX
sudo apt update
sudo apt install samba smbclient
sudo apt install net-tools

sudo useradd -s /bin/bash -m -d /home/x x
sudo smbpasswd -a x
sudo groupadd x
sudo usermod -a -G xg xu

sudo fdisk -l
sudo fdisk /dev/sda
-n
-p
-2
-default
-+2G
-w
sudo mkfs.ext4 /dev/sdax
sudo mount /dev/sdax /xm

sudo mkdir /x
sudo chown xu xm
sudo chgrp xg xm
sudo chmod -R 775 xm

sudo nano /etc/samba/smb.conf
y
y
0660
0750
write list = xu
valid users = xu

sudo testparm
sudo systemctl restart smbd.service

#windows
new-smbmapping -localpath x:\ -remotepath \\0.0.0.0\xl -username xu -password xp


########################windows

[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force
Install-Module -Name NTFSSecurity

diskpart
-list volume
-select volume nx
-shrink desired=x	(v mb)
-exit

get-disk
new-partition -disknumber nx -usemaximumsize -driveletter lx | format-volume -filesystem NTFS -newfilesystemlable ix

mkdir dx

$geslo = ConvertTo-SecureString -String "Password2x" -AsPlainText -Force

new-localuser -name x -password $geslo -accountneverexpires
new-localgroup -name x
add-localgroupmember -group x -name x

Add-NTFSAccess -Path x:\x -Account nx -AccessRights FullControl -AccessType Allow
New-SmbShare -Path x:\x -Name wx
Grant-SmbShareAccess -Name wx -AccountName nx -AccessRight Full

#linux
sudo mkdir /x
sudo chown ax /x
sudo mount //0.0.0.0/w /x -o username=lux,password=x
