
# Vagrantfile and Scripts to Automate Kubernetes Setup using Kubeadm 

## Documentation

Refer this link for documentation: https://devopscube.com/kubernetes-cluster-vagrant/

## Prerequisites

1. Working Vagrant setup
2. 8 Gig + RAM workstation as the Vms use 3 vCPUS and 4+ GB RAM
3. This is suited for ubuntu-like environments
 
## Usage/Examples

To provision the cluster, execute the following commands.

```shell
git clone https://github.com/scriptcamp/vagrant-kubeadm-kubernetes.git
```
```shell
cd vagrant-kubeadm-kubernetes
```
```shell
vagrant up
```

PS: change the IP addr in vagrantfile and master script


## Set Kubeconfig file varaible.

```shell
cd vagrant-kubeadm-kubernetes
```
```shell
cd configs
```
```shell
export KUBECONFIG=$(PWD)/config
```

or you can copy the config file to .kube directory.

```shell
cp config ~/.kube/
```

## Kubernetes Dashboard URL

```shell
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/overview?namespace=kubernetes-dashboard
```

## Kubernetes login token

Vagrant up will create the admin user token and saves in the configs directory.

```shell
cd vagrant-kubeadm-kubernetes
```
```shell
cd configs
```
```shell
cat token
```

## To shutdown the cluster, 

```shell
vagrant halt
```

## To restart the cluster,

```shell
vagrant up
```

## To destroy the cluster, 

```shell
vagrant destroy -f
```
