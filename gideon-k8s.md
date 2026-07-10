498  sudo swapoff -a
  499  free -h
  500  sudo vi /etc/fstab
  501  sudo apt install -y containerd
  502  sudo mkdir -p /etc/containerd
  503  containerd config default | sudo tee /etc/containerd/config.toml
  504  sudo systemctl restart containerd
  505  echo "overlay" | sudo tee /etc/modules-load.d/containerd.conf
  506  echo "br_netfilter" | sudo tee -a /etc/modules-load.d/containerd.conf
  507  sudo modprobe overlay
  508  sudo modprobe br_netfilter
  509  sudo sysctl --system
  510  sudo apt-get install -y apt-transport-https ca-certificates curl gpg
  511  sudo mkdir -p /etc/apt/keyrings
  512  curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.30/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
  513  echo "deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.30/deb/ /" | sudo tee /etc/apt/sources.list.d/kubernetes.list
  514  sudo apt-get update
  515  sudo apt-get install -y kubelet kubeadm kubectl

409a0c5b390df37ea5b34e63840075df672f8ee2b7d72f2966e554bf496c24ae

# Run the member list command through the container
# Replace <CONTAINER_ID> with the ID you found
sudo crictl exec -it d1bde73081e5f etcdctl \
  --endpoints=https://127.0.0.1:2379 \
  --cacert=/etc/kubernetes/pki/etcd/ca.crt \
  --cert=/etc/kubernetes/pki/etcd/server.crt \
  --key=/etc/kubernetes/pki/etcd/server.key \
  member list