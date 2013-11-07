Vagrant.configure("2") do |config|

    # Box configuration.
    config.vm.box       = "precise-docker-64"
    config.vm.box_url   = "http://nitron-vagrant.s3-website-us-east-1.amazonaws.com/vagrant_ubuntu_12.04.3_amd64_virtualbox.box"

    # Network configuration.
    config.vm.network :forwarded_port, host: 8080, guest: 80
    config.vm.network :private_network, ip: "33.33.33.10"

    config.vm.synced_folder ".", "/vagrant", nfs: true

    # Ansible provisioning.
    config.vm.provision :ansible do |ansible|
        ansible.playbook        = "provisioning/playbook.yml"
        ansible.inventory_path  = "provisioning/ansible_hosts"
        ansible.verbose         = "vvvv"
    end
end
