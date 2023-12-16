Install Docker on Ubuntu

Installing Minikube on Ubuntu.

Befehl, um Minikube herunterzuladen

## $ wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
--2023-11-05 23:32:06--  https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
Resolving storage.googleapis.com (storage.googleapis.com)... 142.250.186.91, 172.217.16.155, 142.250.186.123, ...
Connecting to storage.googleapis.com (storage.googleapis.com)|142.250.186.91|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 86435564 (82M) [application/octet-stream]
Saving to: ‘minikube-linux-amd64.1’

minikube-linux-amd64.1        100%[=================================================>]  82.43M  11.4MB/s    in 7.5s

2023-11-05 23:32:13 (11.0 MB/s) - ‘minikube-linux-amd64.1’ saved [86435564/86435564]

mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ 

## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ sudo cp minikube-linux-amd64 /usr/local/bin/minikube
## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ sudo chmod +x /usr/local/bin/minikube
## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ minikube version
minikube version: v1.31.2
commit: fd7ecd9c4599bef9f04c0986c4a0187f98a4396e
mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$

## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   138  100   138    0     0    811      0 --:--:-- --:--:-- --:--:--   811
100 47.5M  100 47.5M    0     0  11.4M      0  0:00:04  0:00:04 --:--:-- 12.4M
## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ chmod +x kubectl
## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ sudo mv kubectl /usr/local/bin/
## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ kubectl version -o yaml
clientVersion:
  buildDate: "2023-10-18T11:42:52Z"
  compiler: gc
  gitCommit: a8a1abc25cad87333840cd7d54be2efaf31a3177
  gitTreeState: clean
  gitVersion: v1.28.3
  goVersion: go1.20.10
  major: "1"
  minor: "28"
  platform: linux/amd64
kustomizeVersion: v5.0.4-0.20230601165947-6ce0bf390ce3

The connection to the server localhost:8080 was refused - did you specify the right host or port?
 mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$
 
The connection to the server localhost:8080 was refused - did you specify the right host or port?
because The connection to the server localhost:8080 was refused
				
we must minikube start:

## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ minikube start --driver=docker
😄  minikube v1.31.2 on Debian 11.8 (amd64)
✨  Using the docker driver based on user configuration
📌  Using Docker driver with root privileges
❗  For an improved experience it's recommended to use Docker Engine instead of Docker Desktop.
Docker Engine installation instructions: https://docs.docker.com/engine/install/#server
👍  Starting control plane node minikube in cluster minikube
🚜  Pulling base image ...
💾  Downloading Kubernetes v1.27.4 preload ...
    > preloaded-images-k8s-v18-v1...:  393.21 MiB / 393.21 MiB  100.00% 6.35 Mi
    > gcr.io/k8s-minikube/kicbase...:  447.62 MiB / 447.62 MiB  100.00% 6.45 Mi
🔥  Creating docker container (CPUs=2, Memory=2200MB) ...
🐳  Preparing Kubernetes v1.27.4 on Docker 24.0.4 ...
    ▪ Generating certificates and keys ...
    ▪ Booting up control plane ...
    ▪ Configuring RBAC rules ...
🔗  Configuring bridge CNI (Container Networking Interface) ...
🔎  Verifying Kubernetes components...
    ▪ Using image gcr.io/k8s-minikube/storage-provisioner:v5
🌟  Enabled addons: default-storageclass, storage-provisioner
🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default
mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$

## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ kubectl version -o yaml
clientVersion:
  buildDate: "2023-10-18T11:42:52Z"
  compiler: gc
  gitCommit: a8a1abc25cad87333840cd7d54be2efaf31a3177
  gitTreeState: clean
  gitVersion: v1.28.3
  goVersion: go1.20.10
  major: "1"
  minor: "28"
  platform: linux/amd64
kustomizeVersion: v5.0.4-0.20230601165947-6ce0bf390ce3
serverVersion:
  buildDate: "2023-07-19T12:14:49Z"
  compiler: gc
  gitCommit: fa3d7990104d7c1f16943a67f11b154b71f6a132
  gitTreeState: clean
  gitVersion: v1.27.4
  goVersion: go1.20.6
  major: "1"
  minor: "27"
  platform: linux/amd64
  
  
  test

## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ kubectl cluster-info
Kubernetes control plane is running at https://127.0.0.1:61631
CoreDNS is running at https://127.0.0.1:61631/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$

## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ kubectl get nodes
NAME       STATUS   ROLES           AGE   VERSION
minikube   Ready    control-plane   10m   v1.27.4
mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$

mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ minikube addons list
|-----------------------------|----------|--------------|--------------------------------|
|         ADDON NAME          | PROFILE  |    STATUS    |           MAINTAINER           |
|-----------------------------|----------|--------------|--------------------------------|
| ambassador                  | minikube | disabled     | 3rd party (Ambassador)         |
| auto-pause                  | minikube | disabled     | minikube                       |
| cloud-spanner               | minikube | disabled     | Google                         |
| csi-hostpath-driver         | minikube | disabled     | Kubernetes                     |
| dashboard                   | minikube | disabled     | Kubernetes                     |
| default-storageclass        | minikube | enabled ✅   | Kubernetes                     |
| efk                         | minikube | disabled     | 3rd party (Elastic)            |
| freshpod                    | minikube | disabled     | Google                         |
| gcp-auth                    | minikube | disabled     | Google                         |
| gvisor                      | minikube | disabled     | minikube                       |
| headlamp                    | minikube | disabled     | 3rd party (kinvolk.io)         |
| helm-tiller                 | minikube | disabled     | 3rd party (Helm)               |
| inaccel                     | minikube | disabled     | 3rd party (InAccel             |
|                             |          |              | [info@inaccel.com])            |
| ingress                     | minikube | disabled     | Kubernetes                     |
| ingress-dns                 | minikube | disabled     | minikube                       |
| inspektor-gadget            | minikube | disabled     | 3rd party                      |
|                             |          |              | (inspektor-gadget.io)          |
| istio                       | minikube | disabled     | 3rd party (Istio)              |
| istio-provisioner           | minikube | disabled     | 3rd party (Istio)              |
| kong                        | minikube | disabled     | 3rd party (Kong HQ)            |
| kubevirt                    | minikube | disabled     | 3rd party (KubeVirt)           |
| logviewer                   | minikube | disabled     | 3rd party (unknown)            |
| metallb                     | minikube | disabled     | 3rd party (MetalLB)            |
| metrics-server              | minikube | disabled     | Kubernetes                     |
| nvidia-driver-installer     | minikube | disabled     | 3rd party (Nvidia)             |
| nvidia-gpu-device-plugin    | minikube | disabled     | 3rd party (Nvidia)             |
| olm                         | minikube | disabled     | 3rd party (Operator Framework) |
| pod-security-policy         | minikube | disabled     | 3rd party (unknown)            |
| portainer                   | minikube | disabled     | 3rd party (Portainer.io)       |
| registry                    | minikube | disabled     | minikube                       |
| registry-aliases            | minikube | disabled     | 3rd party (unknown)            |
| registry-creds              | minikube | disabled     | 3rd party (UPMC Enterprises)   |
| storage-provisioner         | minikube | enabled ✅   | minikube                       |
| storage-provisioner-gluster | minikube | disabled     | 3rd party (Gluster)            |
| volumesnapshots             | minikube | disabled     | Kubernetes                     |
|-----------------------------|----------|--------------|--------------------------------|
mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$


sudo apt update
sudo apt install firefox-esr

firefox-esr http://127.0.0.1:38815/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/

/usr/bin/firefox-esr
/usr/bin/firefox-esr http://127.0.0.1:38815/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/


## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ minikube dashboard
🤔  Verifying dashboard health ...
🚀  Launching proxy ...
🤔  Verifying proxy health ...
🎉  Opening http://127.0.0.1:40885/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/ in your default browser...
[GFX1-]: glxtest: libpci missing
^C
## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ Exiting due to channel error.
Exiting due to channel error.
Exiting due to channel error.
Exiting due to channel error.
Exiting due to channel error.
Exiting due to channel error.
^C
## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ kubectl create deployment nginx-web --image=nginx
deployment.apps/nginx-web created
## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ kubectl get all
NAME                             READY   STATUS    RESTARTS   AGE
pod/nginx-web-6776bdfb8b-cjbvn   1/1     Running   0          39s

NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
service/kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   37m

NAME                        READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/nginx-web   1/1     1            1           39s

NAME                                   DESIRED   CURRENT   READY   AGE
replicaset.apps/nginx-web-6776bdfb8b   1         1         1       39s
mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$

## mohanad@AWSCloud:/mnt/c/Users/Al Mohanad Ilewi/Desktop$ minikube dashboard --url
🤔  Verifying dashboard health ...
🚀  Launching proxy ...
🤔  Verifying proxy health ...
http://127.0.0.1:42859/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/


## mohanad@AWSCloud:~$ minikube start
😄  minikube v1.31.2 on Debian 11.8 (amd64)
✨  Using the docker driver based on existing profile
👍  Starting control plane node minikube in cluster minikube
🚜  Pulling base image ...
🏃  Updating the running docker "minikube" container ...
🐳  Preparing Kubernetes v1.27.4 on Docker 24.0.4 ...
🔎  Verifying Kubernetes components...
    ▪ Using image docker.io/kubernetesui/dashboard:v2.7.0
    ▪ Using image docker.io/kubernetesui/metrics-scraper:v1.0.8
    ▪ Using image gcr.io/k8s-minikube/storage-provisioner:v5
💡  Some dashboard features require the metrics-server addon. To enable all features please run:

        minikube addons enable metrics-server


🌟  Enabled addons: storage-provisioner, default-storageclass, dashboard
🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default
mohanad@AWSCloud:~$

## mohanad@AWSCloud:~$ kubectl version
Client Version: v1.28.3
Kustomize Version: v5.0.4-0.20230601165947-6ce0bf390ce3
Server Version: v1.27.4

mohanad@AWSCloud:~$ minikube status
minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured

mohanad@AWSCloud:~$ minikube stop
✋  Stopping node "minikube"  ...
🛑  Powering off "minikube" via SSH ...
🛑  1 node stopped.
mohanad@AWSCloud:~$

## mohanad@AWSCloud:~$ minikube status
minikube
type: Control Plane
host: Stopped
kubelet: Stopped
apiserver: Stopped
kubeconfig: Stopped

mohanad@AWSCloud:~$

## Ich möchte runtime nicht docker hier start:

mohanad@AWSCloud:~$ minikube start --container-runtime cri-o
😄  minikube v1.31.2 on Debian 11.8 (amd64)
✨  Using the docker driver based on existing profile
👍  Starting control plane node minikube in cluster minikube
🚜  Pulling base image ...
💾  Downloading Kubernetes v1.27.4 preload ...
    > preloaded-images-k8s-v18-v1...:  416.88 MiB / 416.88 MiB  100.00% 11.07 M
🔄  Restarting existing docker container for "minikube" ...
🎁  Preparing Kubernetes v1.27.4 on CRI-O 1.24.6 ...
🔗  Configuring CNI (Container Networking Interface) ...
🔎  Verifying Kubernetes components...
    ▪ Using image gcr.io/k8s-minikube/storage-provisioner:v5
    ▪ Using image docker.io/kubernetesui/dashboard:v2.7.0
    ▪ Using image docker.io/kubernetesui/metrics-scraper:v1.0.8
💡  Some dashboard features require the metrics-server addon. To enable all features please run:

        minikube addons enable metrics-server


🌟  Enabled addons: storage-provisioner, default-storageclass, dashboard
🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default
mohanad@AWSCloud:~$

## Run the following kubectl command to verify that all resources have been installed successfully.

## mohanad@AWSCloud:~$ kubectl get all -n kubernetes-dashboard
NAME                                             READY   STATUS    RESTARTS     AGE
pod/dashboard-metrics-scraper-5dd9cbfd69-4fz5z   1/1     Running   5            9h
pod/kubernetes-dashboard-5c5cfc8747-klb7p        1/1     Running   8 (8h ago)   9h

NAME                                TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)    AGE
service/dashboard-metrics-scraper   ClusterIP   10.102.99.81   <none>        8000/TCP   9h
service/kubernetes-dashboard        ClusterIP   10.101.80.47   <none>        80/TCP     9h

NAME                                        READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/dashboard-metrics-scraper   1/1     1            1           9h
deployment.apps/kubernetes-dashboard        1/1     1            1           9h

NAME                                                   DESIRED   CURRENT   READY   AGE
replicaset.apps/dashboard-metrics-scraper-5dd9cbfd69   1         1         1       9h
replicaset.apps/kubernetes-dashboard-5c5cfc8747        1         1         1       9h
mohanad@AWSCloud:~$