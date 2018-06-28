concourses = {
    "concourse" => "192.168.97.10",
}


Vagrant.configure("2") do |config|
    # always use vagrant insecure key
    config.ssh.insert_key = false
    # forward ssh agent
    config.ssh.forward_agent = true

    check_guest_additions = false
    functional_vboxsf = false

    config.vm.box = "bento/ubuntu-16.04"

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/playbook.yml"
    end

    concourses.each do |name, ip|
      config.vm.define name do |machine|
        machine.vm.hostname = name
        machine.vm.network :private_network, ip: ip
        machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.memory = 3072
          v.cpus = 2
        end
      end
    end
end
