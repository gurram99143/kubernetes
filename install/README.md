* sudo swapoff -a

* sudo sed -i 's/^SELINUX=enforcing$/SELINUX=permissive/' /etc/selinux/config

* sudo dnf install -y iproute-tc
