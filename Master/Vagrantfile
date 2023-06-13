Vagrant.configure("2") do |config|
  config.vm.box = "starboard/ubuntu-arm64-20.04.5"
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.network "private_network", ip: "172.16.129.129"
  config.vm.hostname = "Master"
  config.vm.box_download_insecure = true
  config.vm.provider "virtualbox" do |vb|       # Máy ảo dùng nền tảng virtualbox, với các cấu hình bổ sung thêm cho provider
    vb.name = "master"                      # đặt tên máy ảo tạo ra
    vb.cpus = 2                                # cấp 2 nhân CPU
    vb.memory = "2048"                         # cấu hình dùng 2GB bộ nhớ
  end  
  config.vm.provision "shell", path: "./install.sh"
  # config.vm.provision "shell", inline: <<-SHELL
  #     echo "root password"
  #     echo "123" | passwd --stdin root
  #     sed -i 's/^PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config
  #     systemctl reload sshd
  #     SHELL

end




# To start using your cluster, you need to run the following as a regular user: kubeadm init --apiserver-advertise-address=172.16.129.129 --pod-network-cidr=172.16.0.0/16

#   mkdir -p $HOME/.kube
#   sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
#   sudo chown $(id -u):$(id -g) $HOME/.kube/config

# Alternatively, if you are the root user, you can run:

#   export KUBECONFIG=/etc/kubernetes/admin.conf

# You should now deploy a pod network to the cluster.
# Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
#   https://kubernetes.io/docs/concepts/cluster-administration/addons/

# Then you can join any number of worker nodes by running the following on each as root:

# kubeadm join 172.16.129.128:6443 --token zkog3t.1u2yqm7ua3p3l7ow \
#         --discovery-token-ca-cert-hash sha256:4dd00f4a774342c0c96743bc5b609744ad74c5334969f85508e1abbffc0f604c

kubeadm join 172.16.129.129:6443 --token qq2nnp.9ptm484ajn2frolq \
        --discovery-token-ca-cert-hash sha256:92308d223c34b17b89261e8c6fd5aa587abc889c1f1d873ab1492a65fe24ef77

