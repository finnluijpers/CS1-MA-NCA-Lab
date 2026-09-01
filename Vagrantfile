Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-24.04"
  
  config.vm.provider "vmware_desktop" do |v|
    v.gui = false
    v.vmx["memsize"] = "2048"
    v.vmx["numvcpus"] = "2"
    # Prevent VMware PCI slot assignment warnings on network adapters
    v.vmx["ethernet0.pcislotnumber"] = "160"
    v.vmx["ethernet1.pcislotnumber"] = "224"
  end

  # --- Web Server 1 ---
  config.vm.define "app01" do |app01|
    app01.vm.hostname = "app01"
    app01.vm.network "private_network", ip: "10.0.2.11"
    app01.vm.network "forwarded_port", guest: 80, host: 8081, auto_correct: true
    app01.vm.network "forwarded_port", guest: 3000, host: 3000, auto_correct: true
  end

  # --- Web Server 2 ---
  config.vm.define "app02" do |app02|
    app02.vm.hostname = "app02"
    app02.vm.network "private_network", ip: "10.0.2.12"
    app02.vm.network "forwarded_port", guest: 80, host: 8082, auto_correct: true
  end

  # --- Isolated Database Server ---
  config.vm.define "db01" do |db01|
    db01.vm.hostname = "db01"
    db01.vm.network "private_network", ip: "10.0.2.10"
  end
end