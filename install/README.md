* sudo swapoff -a

* sudo sed -i 's/^SELINUX=enforcing$/SELINUX=permissive/' /etc/selinux/config

* sudo dnf install -y iproute-tc

* master
```
sudo firewall-cmd --permanent --add-port=6443/tcp
sudo firewall-cmd --permanent --add-port=2379-2380/tcp
sudo firewall-cmd --permanent --add-port=10250/tcp
sudo firewall-cmd --permanent --add-port=10251/tcp
sudo firewall-cmd --permanent --add-port=10252/tcp
sudo firewall-cmd --reload
```

* step6
```
sudo vi /etc/modules-load.d/k8s.conf

overlay
br_netfilter

* save & exit

after that
sudo modprobe overlay
sudo modprobe br_netfilter
```

* step7

```
sudo vi /etc/sysctl.d/k8s.conf

net.bridge.bridge-nf-call-iptables  = 1
net.ipv4.ip_forward                 = 1
net.bridge.bridge-nf-call-ip6tables = 1


sudo sysctl --system
```

