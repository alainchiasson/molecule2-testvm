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
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "centos/7"

  config.vm.provider "virtualbox" do |vb|
   # Customize the amount of memory on the VM:
    vb.memory = "1024"
  end

  config.vm.provision "shell", inline: <<-SHELL
    yum install -y epel-release
    yum -y install git
    yum groups install -y "Development Tools"
    yum install -y python34
    yum install -y openssl-devel
    yum install -y docker
    yum install -y python-devel python-pip
    pip install --upgrade pip

    # Prepare for testing.
    pip install tox
    git clone https://github.com/alainchiasson/molecule.git
    cd molecule/
    pip install -r test-requirements.txt -r requirements.txt
    tox
  SHELL
end

# Commands to get this running
#
#    3  yum install -y git
#    4  git clone https://github.com/alainchiasson/molecule.git
#    5  cd molecule
#   13  yum install -y epel-release
#   15  yum install -y python2-pip
#   16  pip install -y tox
#   19  pip install --upgrade pip
#   27  yum install -y python-devel
#   25  yum groups install "Development Tools"
#   20  pip install -r test-requirements.txt -r requirements.txt
#   28  yum search python-dev
#   29  yum install -y python-devel
#   30  pip install -r test-requirements.txt -r requirements.txt
#   31  yum search openssl
#   32  yum install -y openssl-devel
#   33  pip install -r test-requirements.txt -r requirements.txt
#   34  pip install -U -e .
#   35  ls
#   36  molecule dependency
#   37  cd ..
#   38  ls
#   39  ls -l
#   40  molecule init role --role-name testdep
#   41  cd testdep/
#   42  molecule test
#   43  yum install -y docker-common
#   44  molecule test
#   45*
#   46  yum install -y dockerserver
#   47  yum install -y docker-server
#   48  yum search docker
#   49  yum isntall -y docker
#   50  yum install -y docker
#   51  systemctl start docker
#   52  docker ps
#   53  molecule test
#   54  ls
#   55  touch molecule/default/requirements.yml
#   56  echo "- geerlingguy.java" >> molecule/default/requirements.yml
#   57  molecule test
#   58  molecule dependency
#   59  cd ..
#   60  ls
#   61  cd molecule/
#   62  ls
#   63  tox
#   64  ls -l
#   65  history
