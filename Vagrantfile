Vagrant.configure("2") do |config|
  # VM名
  #config.vm.define :www do |c|
  #  define_machine_name c, "vagrant_sample"
  #end
  
  # Ubuntu 14.04LTS
  #config.vm.box = "ubuntu/trusty64"
  # Ubuntu 16.04LTS
  #config.vm.box = "minimal/xenial64"
  # Ubuntu 18.04LTS
  config.vm.box = "bento/ubuntu-18.04"
 
  # IP指定
  config.vm.network "private_network", ip:"192.168.33.60"
  #config.vm.box_version = "20180814.0.0"
 
  # マウント 
  config.vm.synced_folder "./docker", "/vagrant/docker", create: "true"

  # docker の設定
  config.vm.provision :docker, run: "always"

  # docker-compose の設定
  config.vm.provision :docker_compose,
    yml: "/vagrant/docker/docker-compose.yml",
    compose_version: "1.21.2",
    run: "always"
end
