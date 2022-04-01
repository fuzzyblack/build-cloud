# build-cloud
This is Open-stack installation guide with pack-stack. 


#1. Cent-OS 7 setup 
- Set Cent-OS7 minimal edition. 
- Enlarge root directory "(/)" 
  because OpenStack's Operation space is root. 

#2. pre-configure 
- systemctl stop libvirtd 
- systemctl status libvirtd  

- systemctl disable firewalld 
- systemctl stop firewalld 

- systemctl disable NetworkManager 
- systemctl stop NetworkManager 

- systemctl enable network 
- systemctl start network 

- yum install -y https://rdoproject.org/repos/rdo-release.rpm 
- yum update -y 

#3. install PackStack
- yum install -y openstack-packstack 

#4. install OpenStack 
- packstack --allinone --provision-demo=n --os-neutron-ovs-bridge-mappings=extnet:br-ex --os-neutron-ovs-bridge-interfaces=br-ex:enp3s0 --os-neutron-ml2-type-drivers=vxlan,flat

