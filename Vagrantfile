Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.network "public_network"
  config.vm.hostname = "k8s-minikube"
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "main.yml"
  # config.vm.provision "shell", inline: "minikube start --driver=none"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.name = "k8s-minikube"
    end
  end
end
