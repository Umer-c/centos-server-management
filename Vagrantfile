Vagrant.configure("2") do |config| 
    config.vm.box = "jacobw/fedora35-arm64" 
    config.vm.network "private_network", ip: "192.168.56.12"
    config.vm.network "public_network"
    config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"
    config.vm.provider "vmware_desktop" do |vmware|
      vmware.gui = true
      vmware.allowlist_verified = true
      vmware.memory = "1024"
    end
     config.vm.provision "shell", inline: <<-SHELL
       yum install httpd wget unzip vim -y
       systemctl start httpd
       systemctl enabled httpd
       mkdir -p /tmp/finance
       cd /tmp/finance
       wget https://www.tooplate.com/zip-templates/2135_mini_finance.zip
       unzip -o 2135_mini_finance.zip
       cp -r 2135_mini_finance/* /var/www/html/
       systemctl restart httpd
       cd /tmp/
       rm -rf /tmp/finance
     SHELL
  end
