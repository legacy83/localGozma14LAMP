Vagrant.configure("2") do |config|
    config.ssh.forward_agent = true
    config.ssh.insert_key = false

    # Ubuntu 14.04 - Trusty Tahr
    config.vm.define "gozma14" do |gozma14|
        gozma14.vm.box = "geerlingguy/ubuntu1404"
        gozma14.vm.hostname = "gozma14"
        gozma14.vm.network "private_network", ip: "192.168.27.14"
        gozma14.vm.synced_folder "sites/gozma14.local/", "/var/www/gozma14.local/public_html"
        gozma14.vm.synced_folder "sites/adminer.gozma14.local/", "/var/www/adminer.gozma14.local/public_html"
        gozma14.vm.synced_folder "sites/www.gozma14.local/", "/var/www/www.gozma14.local/public_html"
        gozma14.vm.provision "ansible" do |ansible|
            ansible.playbook = "playbook.yml"
        end
    end
end