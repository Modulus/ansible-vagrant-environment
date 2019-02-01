# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

###  yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
# yum install python-pip
# pip install ansible
# yum install sshpass

    N = 3
    (1..N).each do |machine_id|
        #config.
        config.vm.define "node#{machine_id}" do |node|

            node.vm.box = "bento/ubuntu-18.04" #"bento/centos-7.4" #"bento/ubuntu-16.04"
            node.vm.hostname = "node#{machine_id}"
            node.vm.network "private_network", ip: "192.168.79.#{20+machine_id}"
            node.ssh.insert_key = false
            node.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "/home/vagrant/.ssh/id_rsa.pub"
            node.vm.provision "shell", inline: "cat ~vagrant/.ssh/id_rsa.pub >> ~vagrant/.ssh/authorized_keys"
        end
    end
end