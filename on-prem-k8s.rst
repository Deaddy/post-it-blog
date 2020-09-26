A few things to run a k8s on on-prem servers

- use kubeadm to install k8s
- automate install as far as possible
- don't virtualize masters when all other noderes are bare metal
- unless you do not want to expose services to the outside: 
  make sure you have some sort of ingress routing, e.g. HAProxy w/ HostNetwork
  on a machine on the edge, pointing at a nginx-ingress daemonset on selected
  nodes
- when using nginx ingress on machines w/ more than 16 cores make sure to set
  workers and in general you need to look at the config then
- make sure you have some sort of dynamic volume provisioning in place; cephfs
  is easy to setup and volume provisioners exist
- if you can backup to something outside the cluster rook ceph is a low-config
  option for providing ceph
