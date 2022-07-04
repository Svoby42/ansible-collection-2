sudo apt-get install qemu virt-manager virt-viewer dnsmasq vde2 bridge-utils openbsd-netcat libguestfs

sudo rc-service libvirtd start
sudo rc-update add libvirtd
sudo vim /etc/libvirt/libvirtd.conf 

and set unix_sock_group = "libvirt"
	unix_sock_ro_perms = "0777"
	unix_sock_rw_perms = "0770"

then add yourself to libvirt group

sudo usermod -aG libvirt $USER

then reboot and restart libvirtd
