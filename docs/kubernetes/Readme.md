Day 1 - 23rd Dec 2019

High level agenda

- Go through Mumshad all k8s notes
   
- Create K8s cluster using kthw and kubeadm
a. Create K8s cluster using kubeadm in LA.

As exam will be based on Ubuntu 16 machines so will be spawning 4 nodes using kubeadm

Setup in mind -

a. Initially go with 1 master node and 3 worker nodes, with each node having different labels to test various conditions.

Going via the documentation - main k8s docs are divided into

1. Getting started -- CNI used Weave - use all 
   1. Contains release notes
   2. Getting started with minikube - simple k8s commands w.r.t minikube
   3. Details about production runtime - installing cri includes docker, cri-o, containerd 
      1. Refer for steps if need to install docker
   4. Installing k8s with tools including kubeadm, kops, krib, kubespray.
      a. Main focus is on kubeadm as it will be covered in the exam
         1. information about the ports for different k8s components is present here, and installing kubeadm itself
         2. kubeadm cluster init, token and join with worker nodes
            1. `netstat -nlpt|grep :10250` --> to check if a port is currently in use
         3. creating HA kubeadm cluster 
            1. Topology Same ETCD same API server , use upload certs and then use the command to join with other nodes,
                use private ip of first etcd or use dns of loadbalancer
                    `kubeadm init --control-plane-endpoint "172.31.105.97:6443" --upload-certs`
            2. Separte ETCD servers refer to file and configure separte etcd urls
                `kubeadm config print init-default`
                use command 
                `kubeadm init --config kubeadm-config.yaml --upload-certs` then to create the cluster and install CNI
      b. Turnkey solutions , on premise and windows
    5. Best Practices - Read them 
       1. Important information about the certificates that needs to be generated for different k8s component is mentioned, refer to this page when doing **KTHW**
2. Concepts
3. Tasks
4. Tutorials
5. Reference