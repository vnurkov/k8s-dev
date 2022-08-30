$script = <<-SCRIPT
echo "Download and install crictl ..."
curl -L https://github.com/kubernetes-sigs/cri-tools/releases/download/$VERSION/crictl-${VERSION}-linux-amd64.tar.gz --output crictl-${VERSION}-linux-amd64.tar.gz
sudo tar zxvf crictl-$VERSION-linux-amd64.tar.gz -C /usr/local/bin
rm -f crictl-$VERSION-linux-amd64.tar.gz
echo "Provision script COMPLETED !"
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network "public_network"
  config.vm.hostname = "k8s-minikube"
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "provision.yml"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.name = "k8s-minikube"
    end
  end
end
