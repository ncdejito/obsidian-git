[[Workspace]]

```
# --------------------------------
# Setup script for linux on windows via vagrant box
# source: https://ifcuriousthenlearn.com/blog/2015/08/18/vagrant-linux/
# --------------------------------

vagrant box add bento/ubuntu-18.04
# or hashicorp/precise64 for a 12.04 LTS 64 machine
# or chef/ubuntu-14.04  for a base 14.04 LTS 64 ubuntu machine

## Setup a work folder ----
# make a new folder called vagrant_test
# mkdir vagrant_test

# change directory to vagrant test
# cd vagrant_test
cd ~/Downloads

# print working directory to check the file path
pwd

## Initialize a new Vagrant project ----
# initializes this vagrant session with the image we downloaded
vagrant init bento/ubuntu-18.04

# starts the virtual machine
vagrant up

## Access your brand new Linux machine on Windows! ----
# using ssh to access the shell of your machine
vagrant ssh

# and when finished exit ssh
exit

## Using File Sync ----
# config.vm.synced_folder "C:/Users/ncdejito/Downloads", "/home/vagrant"#, type: "rsync", rsync__auto: true, rsync__exclude: ['.ssh/']
# to use rsync__exclude, you need to run 'vagrant rsync-auto' first https://github.com/hashicorp/vagrant/issues/3350
# create a directory called test
mkdir /vagrant/test

# create a file called test.txt and add a string to it
echo "testing the files sync in a vagrant VM" >> /vagrant/test/test.txt

## Reloading, Stopping, and Starting ----
# To reload a VM and reload any new changes in the Vagrantfile config run
vagrant reload

# When complete and want to exit, run
vagrant halt

# When you are ready to start working again and starting fresh
vagrant up

# Running scripts and Installing programs
sudo apt-get install dos2unix
dos2unix script.sh

# Installing python
git clone http://github.com/nagordon/vagrant-miniconda.git
cd vagrant-miniconda
vagrant up
vagrant ssh

# downloads miniconda
wget http://repo.continuum.io/miniconda/Miniconda-latest-Linux-x86_64.sh

# makes the miniconda installation executable
chmod +x Miniconda-latest-Linux-x86_64.sh

# installs miniconda manually. Make sure you select yes for adding the path. Also spacebar to skip the documentation at the beginning
bash Miniconda-latest-Linux-x86_64.sh

# remove the downloaded fil
rm Miniconda-latest-Linux-x86_64.sh

exit
vagrant ssh

conda install pip -y
conda install numpy -y
conda install ipython -y
conda install matplotlib -y
conda install pandas -y
conda install numpy -y
conda install ipython-notebook -y

# -----------------------------------
# Github auth
# -----------------------------------

# Check if has files like id_rsa.pub
ls -al ~/.ssh

# Generate if none
ssh-keygen -t rsa -b 4096 -C "ncdejito@gmail.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
# chmod 400 ~/.ssh/id_rsa

# paste this to Github/Settings/SSH and GPG keys
cat ~/.ssh/id_rsa.pub

# test connection if working
ssh -T git@github.com

# -----------------------------------
# Existing way to get Github acess to work
# (pero medj hassle)
# -----------------------------------

# add rsync line in vagrant file

vagrant reload
vagrant rsync-auto
vagrant ssh

# perform github adding ssh keys here
```