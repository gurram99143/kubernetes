* woreked one https://swapnasagarpradhan.medium.com/install-a-kubernetes-cluster-on-rhel8-with-conatinerd-b48b9257877a


```
cat > /etc/modules-load.d/containerd.conf <<EOF
overlay
br_netfilter
EOF
modprobe overlay
modprobe br_netfilter
# Setup required sysctl params, these persist across reboots.
cat > /etc/sysctl.d/99-kubernetes-cri.conf <<EOF
net.bridge.bridge-nf-call-iptables  = 1
net.ipv4.ip_forward                 = 1
net.bridge.bridge-nf-call-ip6tables = 1
EOF
sysctl --system

```

```
### Install required packages
dnf install -y  yum-utils device-mapper-persistent-data lvm2


## Add docker repository
dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
Adding repo from: https://download.docker.com/linux/centos/docker-ce.repo
[root@k8master yum.repos.d]# dnf update -y && dnf install -y containerd.io

## Configure containerd
mkdir -p /etc/containerd
containerd config default > /etc/containerd/config.toml
# Restart containerd 
systemctl restart containerd
# Enable containerd on boot 
root@k8master ~]# systemctl enable containerd
```

```
# Add yum repo file for Kubernetes  
# cat <<EOF > /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
EOF
#Install Kubernetes (kubeadm, kubelet and kubectl) 
[root@k8master ~]# dnf install -y kubeadm-1.17.0 kubelet-1.17.0 kubectl-1.17.0
```

[root@k8master ~]# systemctl enable kubelet
[root@k8master ~]# echo 'KUBELET_EXTRA_ARGS="--fail-swap-on=false"' > /etc/sysconfig/kubelet
[root@k8master ~]# systemctl start kubelet

```
```
[root@k8master]# kubeadm init --pod-network-cidr=192.168.0.0/16
--
--
--
Your Kubernetes control-plane has initialized successfully!
```

```
kubectl apply -f https://docs.projectcalico.org/manifests/calico.yaml

```
kubectl get nodes 
```
