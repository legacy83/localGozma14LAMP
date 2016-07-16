Vagrant.configure("2") do |config|
    config.ssh.forward_agent = true
    config.ssh.insert_key = false

    # Ubuntu 12.02 - Precise Pangolin
    config.vm.define "gozma12" do |gozma12|
        gozma12.vm.box = "geerlingguy/ubuntu1204"
        gozma12.vm.hostname = "gozma12"
        gozma12.vm.network "private_network", ip: "192.168.27.12"
        config.vm.synced_folder "sites/gozma12.local/", "/var/www/gozma12.local/public_html"
        config.vm.synced_folder "sites/adminer.gozma12.local/", "/var/www/adminer.gozma12.local/public_html"
        config.vm.synced_folder "sites/www.gozma12.local/", "/var/www/www.gozma12.local/public_html"
        config.vm.provision "ansible" do |ansible|
            ansible.playbook = "playbook.yml"
        end
    end
end