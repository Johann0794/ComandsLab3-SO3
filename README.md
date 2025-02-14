Comandos usados practica 1
============================================
sudo nano /etc/default/grub
sudo update-grub
mount -o rw,remount /
passwd root
reboot

Comandos usados practica 2
============================================
nano backup_home.sh
#!/bin/bash
fecha=$(date +"%d-%m-%Y:%H:%M")
tar -czvf /home/$(whoami)/backup_$fecha.tar.gz /home/$(whoami)

chmod +x backup_home.sh
./backup_home.sh
nano ifconfig_to_file.sh
#!/bin/bash
echo "¿Qué nombre desea ponerle al archivo?"
read nombre_archivo
ifconfig > /home/$(whoami)/Escritorio/$nombre_archivo.txt

chmod +x ifconfig_to_file.sh
./ifconfig_to_file.sh

Comandos usados practica 3
============================================
ifconfig

ping 192.168.0.107

sudo apt update
sudo apt install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh

ssh johannsel@192.168.0.107

ssh-keygen -t rsa -b 4096
scp C:\Users\agner\.ssh\id_rsa.pub johannsel@192.168.0.107:/home/johannsel/

ls /home/johannsel/
mkdir -p ~/.ssh
cat /home/johannsel/id_rsa.pub >> ~/.ssh/authorized_keys
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
rm /home/johannsel/id_rsa.pub

ssh johannsel@192.168.0.107
