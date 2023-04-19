# Provisioning MongoDB
put these codes into the vagrantfile for two machines, app and db
<img width="694" alt="Screenshot 2023-04-19 at 15 15 22" src="https://user-images.githubusercontent.com/129948378/233112420-85fc29bd-8894-4a8d-b678-21a6f0774600.png">
* We can change the name by adding `config.vm.define "app" do |app|`. 
* Change `app` to whatever name you want it to be.
* We then can change where `config` is to the VM name and in this case it is `app`.
* Be sure to add `end` to the `config ....` lines.


