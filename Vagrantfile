# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "eurolinux-vagrant/centos-stream-9"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.56.24"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Disable the default share of the current code directory. Doing this
  # provides improved isolation between the vagrant box and your host
  # by making sure your Vagrantfile isn't accessable to the vagrant box.
  # If you use this you may want to enable additional shared subfolders as
  # shown above.
  # config.vm.synced_folder ".", "/vagrant", disabled: true

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
   config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
     vb.memory = "1024"
   end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
   config.vm.provision "shell", inline: <<-SHELL
     yum install httpd wget unzip -y 
     systemctl start httpd
     systemctl enabled httpd
     mkdir -p /tmp/blog
     cd /tmp/blog
     wget --header="Host: drive.usercontent.google.com" --header="User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/126.0.0.0 Safari/537.36" --header="Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8" --header="Accept-Language: pt-BR,pt;q=0.9" --header="Cookie: SEARCH_SAMESITE=CgQIqJsB; HSID=AOMMxMrYk0eQ8TAq-; SSID=AwEbqmk72olAq6n1E; APISID=tzldYAltySeiaqoO/AcBZc56jJ6HCsWNRL; SAPISID=BWja310A8ryaWRr-/AiAWncgpw2_bYF12y; __Secure-1PAPISID=BWja310A8ryaWRr-/AiAWncgpw2_bYF12y; __Secure-3PAPISID=BWja310A8ryaWRr-/AiAWncgpw2_bYF12y; SID=g.a000lgi1QfLDU4UEtDQXF_zYeKTny6UdIfsKFhTgQC2o0WSZh9QVw1FAw1NPcIN0aCVj5g_1lAACgYKAbgSARQSFQHGX2MixKqBehMWlc6RqZ51xwN5dBoVAUF8yKq0i1v6xBzyP8HanogaxMds0076; __Secure-1PSID=g.a000lgi1QfLDU4UEtDQXF_zYeKTny6UdIfsKFhTgQC2o0WSZh9QVPoJMRSP3-sd_gHT5k6QI1AACgYKAZASARQSFQHGX2MiLtVEqvnxzXfQhstp5XtFABoVAUF8yKpWdg3y9P4R3RRk4S9pNiRQ0076; __Secure-3PSID=g.a000lgi1QfLDU4UEtDQXF_zYeKTny6UdIfsKFhTgQC2o0WSZh9QVZkNxAgFC7gfW2lBkeJOHXwACgYKAeUSARQSFQHGX2MiGiZ2xkJv3-ebsve8lIWQRhoVAUF8yKrosRBe5q5g8pnAxri6qszp0076; AEC=AVYB7cotv-a_n_lj4yYEHjidFX7Fj-qQsOBW7Gsv3WH3VVZoiEsuqhAonng; OGPC=19025003-1:; NID=516=hg7GOtoB3AolgaFmEjdGvbyA617YVT6tFlZ3oo-eGBOXTTXCTUNxfh-bSC2EFq1HaEA1nrEdNxlz6y4qHkcWquHXgTR8ESO1Cl4U1VqTvpluzpKfRynrWGP133QlxQE9bZCWt0oCXNUsnPBBu5SJ0WPIui4hwrmYxx_Zh2xjm1FNLpOA5kAP7SyqXIIPNbsYCFjx4cPjCyH36U9KxM1qqv9oeX2-HEVUEnUFbIjggnwGVlgdHR3aK2TqdHxSksIypTHURpo8fPykH2iDtxKC8dPdmgPNmZm4J1AZZegVbJr2vaSvwb6uOeGg2havJCXWIvTKCWY8EaeSFgtNXKx2oorkeINT0JN34HG6-McMNfMjLDkwdf7MszNLZaUPQzmwAz99Wp5zIEfZ3glI4MSNFwg_cqwdF-WwWE5kYE1RakAWLTDSDKImTBZBUiu2S_4mLzwjY_KktwW2AgTSIhd3DhrOdU13iklZn0-i0fDM1JB-mUU2Qm-3ScA9Xoqhao2bp-rNxk9z8389fUWnL5O4pRYKVRAVeytiumS2QTho; __Secure-1PSIDTS=sidts-CjEB4E2dkUR-IHS-eBg2gxsvrM2ZRkgVipA9kPAP1RGJffbhiL8OeiPzPfP3nEVSUCL4EAA; __Secure-3PSIDTS=sidts-CjEB4E2dkUR-IHS-eBg2gxsvrM2ZRkgVipA9kPAP1RGJffbhiL8OeiPzPfP3nEVSUCL4EAA; SIDCC=AKEyXzVTtX5ZKPzZ5F6rziT6BZmQDDy-WT6BY60Ju7r9gqSUUquRH0ncXwomNCfWhxq9-r3QwJo; __Secure-1PSIDCC=AKEyXzVvo5o-_Er_jcoT6h_4nAtw5mQys0qRkv5R2cnP5U8R2eaaZHFl17JFqijvp3YsUv9jtaQ; __Secure-3PSIDCC=AKEyXzXJTCsjlOa51Ts6J676BhBx7dhgy7-9XzqlceJuaW0IUpjHZ_-yXS3tYquv4LsY42NsgQ" --header="Connection: keep-alive" "https://drive.usercontent.google.com/download?id=1iET9WESCpysKE_NdH5TI5bCq_HN92G-B&export=download&authuser=0&confirm=t&uuid=c25494aa-b44b-4b91-ad4d-26292ec248ee&at=APZUnTVMSwmFG8kjecVRqNTMDudd:1721673378296" -c -O 'xtra_blog_modelo.zip'
     unzip -o xtra_blog_modelo.zip 
     sudo cp -r templatemo_553_xtra_blog/* /var/www/html
     systemctl restart httpd
     cd /tmp/
     rm -rf /tmp/blog
   SHELL
end
