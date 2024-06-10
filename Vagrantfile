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
  end
