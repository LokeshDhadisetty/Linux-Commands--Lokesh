find /sapdb_backups -xdev -size +1G -type f -exec ls -lhtr {} \;
 
free -h;free -m | awk '/Mem/ {print "free memory space ="($4/$2)*100"%"}';date
free -h;free | awk '/Swap/ { print "Swap usage is "($3/$2)* 100 " %"} '; date
 
ps aux --sort -rss | head -2 ; date
 
 
free -h;ps aux| awk '{print $2, $4, $11}'|head -1;ps aux | awk '{print $2, $4, $11}' | sort -k2rn | head -n 10;echo;free|awk '/Swap/ {print "Swap usage is "($3/$2)*100"%"}';date   ----- swap utilization
=======================================================================================================================


####  Patching commands   ###################


uptime
uname -a
date
ifconfig -a
netstat -rn
df -h
cat /etc/fstab
ls -l /etc/localtime
for i in $(grep -v ^# /etc/fstab | awk {'print $2'} | sort | grep -v ^swap$ ); do mountpoint -q $i || echo "$i not mounted" ; done
yum history
yum list updates
route -n
yum check-update
cat /etc/hosts
yum -x mtr,nginx,rsyslog update

yum update --exclude=gcc,php----to exclude package 
dsmc q fi  ---- backup information

======================================================
uname -a; uptime; date; df -TPh |wc -l; df -TPh; pvscan; lvscan; netstat -rn; netstat -rn | wc -l; ifconfig -a;
cat /etc/os-release; cat /etc/hosts; ps -ef |grep dsmc ; free -m ; nproc; pvs ; lvs ; rpm -qa --last |grep -i kernel* ; ls -ld /etc/resolv.conf ; cat /etc/resolv.conf ; yum check-update ; sestatus;cat /proc/mounts |grep -i ro,

==============================================================================



subscription-manager list --available      ---sub manag available or not 
CS14043364

uptime; uname -a; df -h ;df -h |wc -l; cat /etc/fstab; /sbin/ifconfig -a; netstat -rn;netstat -rn|wc -l yum check-update; 

/usr/sbin/dmidecode |grep -i product; cat /etc/resolv.conf; cat /etc/hosts; cat /etc/exports;ls -l /etc/localtime; yum history; yum repolist all; cat /etc/yum.repos.d/redhat.repo;  cat /etc/grub.conf; pvs; lvs; vgs; blkid; lsblk; fdisk -l;date
pvs; lvs; vgs; blkid; lsblk; fdisk -l;date
cat /etc/redhat-release
systemctl status sshd  
service nfs status;service postfix status
grep -i zone /etc/sysconfig/clock
dsmc q fi
ls -l /etc/localtime
for i in $(grep -v ^# /etc/fstab | awk {'print $2'} | sort | grep -v ^swap$ ); do mountpoint -q $i || echo "$i not mounted" ; done
yum history
yum list updates
which salt-call
salt-call grains.item nodename host fqdn

yum update -y

du -a / |sort +n
===================================================
sudo zypper list-updates --all
sudo zypper list-patches
uptime; uname -a;  cat /etc/os-release;
df -h ;df -h |wc -l;
cat /etc/fstab;
ifconfig -a; ip a
netstat -rn;netstat -rn|wc -l;  or  ip route or  route -n
cat /etc/resolv.conf;
cat /etc/hosts;
cat /etc/exports;
ls -l /etc/localtime;
pvs; lvs; vgs; blkid; lsblk; fdisk -l
service nfs status;service postfix status;service chronyd status
dsmc q fi
for i in $(grep -v ^# /etc/fstab | awk {'print $2'} | sort | grep -v ^swap$ ); do mountpoint -q $i || echo "$i not mounted" ; done
suse patching 


# zypper repos
to list updates:
zypper list-updates | cut -s -d"|" -f3,4,5
Install the latest packages for this release with no interaction
# zypper --non-interactive up

nstead of ifconfig -a -- use-- ip a
instead of netstat -nr -  use-- ip route


zypper lr  - in outut Enabled should be Yes
zypper list-updates | cut -s -d"|" -f3,4,5  - it should list packages

to solve repos issue --- zypper mr -e (number)

zypper mr -e (number)
zypper ref---to refresh
