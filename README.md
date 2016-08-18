# Kubernetes Cluster on single machine (ubuntu 14.04)

**step-1:**

```
$ sudo -s # Login as a root user privilege
$ ./01_docker-install 
	
```

Above command will install docker. 

**step-2:**

```
$ ./02_other-dependency	
```
Above command will install socat and kubectl

**step-3:**

```
$ ./03_bootstrap-cluster up
```
Above command will download all Kubernetes moving parts and configure cluster


## Addons
03_bootstrap-cluster also sets up:
* The [DNS addon](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/dns)
* The [Kubernetes Dashboard](https://github.com/kubernetes/dashboard)

## Example Laravel Appalication deployment

```
$ cd example
$ kubectl create -f demo-app.yaml # Create ReplicationControler and Service
```

We have expose node port for external access.

```
$ kubectl describe svc demo-app
```

You will find the port number on Nodeport section. 

Hit http://your_kubernetes_ip:port on browser. 


