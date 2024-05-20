# How2InstallCapeSandbox-
How2InstallCapeSandbox 

sudo apt-get update && sudo apt-get upgrade -y
sudo chmod -R a+rwx /opt/
cd /opt
sudo apt install git
git clone https://github.com/kevoreilly/CAPEv2.git
cd CAPEv2/installer
sed -i 's/<WOOT>/BXPC/g' kvm-qemu.sh
chmod a+x kvm-qemu.sh
chmod a+x cape2.sh
-------------------------------------------------
sudo ./kvm-qemu.sh all cape | tee kvm-qemu.log
sudo reboot

cd /opt/CAPEv2/installer
sudo ./kvm-qemu.sh virtmanager cape | tee kvm-qemu-virt-manager.log

cd /opt/CAPEv2/installer
sudo ./cape2.sh all cape | tee cape.log
sudo reboot

cd /opt/CAPEv2
poetry install
poetry env list
---- poetry run pip install -r requirements.txt -------
sudo -u cape poetry run pip install -r extra/optional_dependencies.txt
sudo -u cape poetry run pip install pyattck==7.1.2
-----------------------------
cd /opt/CAPEv2
sudo apt install dbus-x11
sudo poetry install
-----------------------------
nano /opt/CAPEv2/conf/cuckoo.conf
under [resultserver]
ip = *yourip VM IP* example: 192.168.122.1

nano /opt/CAPEv2/conf/kvm.conf
add VM info like name, label, platfarm, ip ...etc
-----------------------------

sudo dpkg -i --force-overwrite /var/cache/apt/archives/qemu-system-data_1%3a6.2+dfsg-2ubuntu6.19_all.deb

sudo dpkg -i --force-overwrite /var/cache/apt/archives/qemu-system-x86_1%3a6.2+dfsg-2ubuntu6.19_amd64.deb

sudo dpkg -i --force-overwrite /var/cache/apt/archives/qemu-utils_1%3a6.2+dfsg-2ubuntu6.19_amd64.deb

sudo dpkg -i --force-overwrite /var/cache/apt/archives/qemu-system-common_1%3a6.2+dfsg-2ubuntu6.19_amd64.deb

sudo apt --fix-broken install

sudo apt-get install virt-manager

