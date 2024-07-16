# Gitlab-project

STEP1
Create a repository
https://github.com/jaiswaladi246/Boardgame.git
Create a Runner and register the runner
Create a pipeline (refer the file .gitlab-ci.yaml)
 
docker run -d -p 9000:9000 sonarqube:lts-community
Create a cluster 
Run the below commands on both master and slave

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


make a script for the above commands and run it on both master and slaves

enter the below command in the master 
sudo kubeadm init --pod-network-cidr=10.244.0.0/16   # this command will generate a token to join slave with master

# Run the output of above command in worker node

mkdir -p $HOME/ .kube
sudo cp -i /etc/Kubernetes/admin.conf $HOME/ .kube/config
sudo chown $(id -u) :$(id -g) $HOME/.kube/config
kubectl apply -f https://raw.githubusercontent.com/projectcalico/calico/v3.24.0/manifests/calico.yaml                   calico used for networking

kubectl apply -f https://githubusercontent.com/kubernetes/ingress-nqinx/controller-v0.49.0/deploy/static/provider/baremetal/deploy.yaml


![image](https://github.com/user-attachments/assets/a2a262c4-bd29-45ed-acfb-5b6d9c2123d2)

![image](https://github.com/user-attachments/assets/41f86d95-5752-4c14-abe9-5254796e31c9)

