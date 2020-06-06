Put questions here which will be looked into later

1. check number of cpu, memory in a linux system to check if they fulfil the requirements.
2. Ip tables
3. what are linux sockets
4. Check what is the CRI in test cluster --> IMPORTANT
5. Refer https://docs.docker.com/config/daemon/systemd/ -- Starting docker with systemd
6. SSL cert - `openssl x509 -text -noout`
7. for kubeadm to use external ca - https://gist.github.com/detiber/81b515df272f5911959e81e39137a8bb


Links to go to
https://gist.github.com/texasdave2/8f4ce19a467180b6e3a02d7be0c765e7
https://github.com/David-VTUK/CKA-StudyGuide/tree/master/LabGuide
https://github.com/walidshaari/Kubernetes-Certified-Administrator

https://www.objectif-libre.com/en/blog/2018/07/05/k8s-network-solutions-comparison/

Generate CA client certificate for API server to communicate with ETCD
```
    openssl x509 -req -in /etc/kubernetes/pki/apiserver-etcd-client.csr \
        -CA /etc/kubernetes/pki/etcd/ca.crt \
        -CAkey /etc/kubernetes/pki/etcd/ca.key \
        -CAcreateserial \
        -out /etc/kubernetes/pki/apiserver-etcd-client.crt
```
Have to create CSR in that case, do check if there is a CSR present.