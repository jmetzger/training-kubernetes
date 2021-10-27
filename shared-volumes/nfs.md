# SharedVolume with NFS

## Create new server and install nfs-server

```
# on Ubuntu 20.04LTS
apt install nfs-kernel-server 
systemctl status nfs-server 

vi /etc/exports 
# adjust ip's of kubernetes master and nodes 
# kmaster
/var/nfs/ 192.168.56.101(rw,sync,no_root_squash,no_subtree_check)
# knode1
/var/nfs/ 192.168.56.103(rw,sync,no_root_squash,no_subtree_check)
# knode 2
/var/nfs/ 192.168.56.105(rw,sync,no_root_squash,no_subtree_check)

exportfs -av 
```

## On all clients 

```
### Please do this on all servers 

apt install nfs-common 
# for testing 
mkdir /mnt/nfs 
# 192.168.56.106 is our nfs-server 
mount -t nfs 192.168.56.106:/var/nfs /mnt/nfs 
```
