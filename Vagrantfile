VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/bionic64"

  machines = {
    "master" => "192.168.56.10",
    "node01" => "192.168.56.11",
    "node02" => "192.168.56.12",
    "node03" => "192.168.56.13"
  }

  machines.each do |name, ip|
    config.vm.define name do |node|
      node.vm.hostname = name
      node.vm.network "private_network", ip: ip
      node.vm.provider "virtualbox" do |vb|
        vb.memory = 1024
        vb.cpus = 1
      end
      node.vm.provision "shell", path: "scripts/install_docker.sh"
    end
  end
end
