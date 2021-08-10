Vagrant.configure("2") do |config|
    config.trigger.before :up do |trigger|
        trigger.info = "Creating 'NATSwitch' Hyper-V switch if it does not exist..."
    
        trigger.run = {privileged: "true", powershell_elevated_interactive: "true", path: "./scripts/create-nat-hyperv-switch.ps1"}
    end
    
    config.trigger.before :reload do |trigger|
        trigger.info = "Setting Hyper-V switch to 'NATSwitch' to allow for static IP..."
    
        trigger.run = {privileged: "true", powershell_elevated_interactive: "true", path: "./scripts/set-hyperv-switch.ps1"}
    end
    
    config.vm.provision "shell", path: "./scripts/centos/configure-static-ip.sh"
    
    config.vm.provision :reload

    config.vm.provider "hyperv" do |hv|
        hv.vmname = "homestead"
    end
    config.vm.hostname = "hypervhost"
    config.vm.synced_folder '.', '/vagrant', {
      type: 'smb', mount_options: ['vers=3.0'],
      smb_username: ENV['VAGRANT_SMB_USERNAME'],
      smb_password: ENV['VAGRANT_SMB_PASSWORD']
    }
    config.vm.box = "centos/7"
end