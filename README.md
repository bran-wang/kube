# kube
all in one kubernetes cluster install

1. stop firewalld
systemctl disable firewalld
systemctl stop firewalld

2. install etcd and kubernetes
yum install -y etcd kubernetes

3. modify conf
/etc/sysconfig/docker
OPTIONS='--selinux-enabled=false --insecure-registry gcr.io'
/etc/kubernetes/apiserver
del --admission_control 's ServiceAccount

4. start all services
systemctl start etcd
systemctl start docker
systemctl start kube-apiserver
systemctl start kube-controller-manager
systemctl start kube-scheduler
systemctl start kubelet
systemctl start kube-proxy
