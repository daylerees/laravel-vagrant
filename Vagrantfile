Vagrant.configure("2") do |config|

    # Box configuration.
    config.vm.box       = "precise64"
    config.vm.box_url   = "http://files.vagrantup.com/precise64.box"

    # Network configuration.
    config.vm.network :forwarded_port, host: 8080, guest: 80
    config.vm.network :private_network, ip: "192.168.50.50"

    # Filesystem configuration. (Uncomment if access to NFS)
    # config.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"], :nfs => true

    # Ansible provisioning.
    config.vm.provision :ansible do |ansible|
        ansible.playbook        = "provisioning/playbook.yml"
        ansible.inventory_path  = "provisioning/ansible_hosts"
        ansible.verbose         = "vv"
    end
end
