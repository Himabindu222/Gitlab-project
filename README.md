# Gitlab-project

#STEP1

Create a repository in the gitlab
(https://github.com/jaiswaladi246/Boardgame.git)

#STEP2

Create a Runner and register the runner

settings -> ci/cd -> Runners

(create an instance and run commands given in the console while creating the runner)

#STEP3

Create a pipeline (refer the file .gitlab-ci.yaml)

Build -> pipeline editor
 

#STEP4

Create a cluster 

Run below commands on both master and slave

sudo apt-get update
sudo apt install docker.io
sudo chmod 666 /var/run/docker.sock
sudo apt-get install -y apt-transport-https ca-certificates curl gnupg
sudo mkdir -p -m 755 /etc/apt/keyrings
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.30/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
echo 'deb [signed-by-/etc/apt/keyrings/kubernetes-apt-keyring.gpg]
https://pkqs.k8s.io/core:/stable:/v1.30/deb/ /' | sudo tee /etc/apt/sources.list.d/Kubernetes.list
sudo apt update
sudo apt install -y kubeadm=1.30.0-1.1 kubelet=1.30.0-1.1 kubectl-1.30.0-1.1

OR 

make a script for the above commands and run it on both master and slaves
enter below command in the master 
sudo kubeadm init --pod-network-cidr=10.244.0.0/16   # this command will generate a token to join slave with master, Run the output of this command in worker node

mkdir -p $HOME/ .kube
sudo cp -i /etc/Kubernetes/admin.conf $HOME/ .kube/config
sudo chown $(id -u) :$(id -g) $HOME/.kube/config
kubectl apply -f https://raw.githubusercontent.com/projectcalico/calico/v3.24.0/manifests/calico.yaml                   calico used for networking

kubectl apply -f https://githubusercontent.com/kubernetes/ingress-nqinx/controller-v0.49.0/deploy/static/provider/baremetal/deploy.yaml

![image](https://github.com/user-attachments/assets/62e332a2-e1f1-4f05-a740-96edfa9e4f6f)
![image](https://github.com/user-attachments/assets/41f86d95-5752-4c14-abe9-5254796e31c9)
![image](https://github.com/user-attachments/assets/a2a262c4-bd29-45ed-acfb-5b6d9c2123d2)
