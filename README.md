# Provisioning MongoDB
### put these codes into the vagrantfile
<img width="694" alt="Screenshot 2023-04-19 at 15 15 22" src="https://user-images.githubusercontent.com/129948378/233113738-6d7c7d70-ea2f-444a-a917-215368f0e9c9.png">
rantfile 

* We can change the name by adding `config.vm.define "app" do |app|`. 
* Change `app` to whatever name you want it to be.
* We then can change where `config` is to the VM name and in this case it is `app`.
* Be sure to add `end` to the `config ....` lines.

### Virtual Machine(s) should be listed below in Virtualbox as such 
<img width="759" alt="Screenshot 2023-04-19 at 15 51 21" src="https://user-images.githubusercontent.com/129948378/233114291-ea64ede0-323f-4e9a-826c-d56d12bdf349.png">

### Provisioning MongoDB
  We create a new provision file for our db virtual machine, we name it `provisiondb.sh` and the contents are shown below :

```
# updates the package list on the Ubuntu system and installs the latest version of all packages.

sudo apt update -y

# upgrades all installed packages to the latest version.

sudo apt upgrade -y

# adds  MongoDB  key so we can authenticate packages from MongoDB repository

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv D68FA50FEA312927

# adds the MongoDB repository to the system's list of repositories

echo "deb https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list

# We now update and upgrade again but now this includes the MongoDB repository and MongoDB to latest version

sudo apt update -y

sudo apt upgrade -y

# installs the MongoDB package and its associated components, including the server, shell, router, and tools

sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20


