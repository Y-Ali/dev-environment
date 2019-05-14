##DevEnvironments using Vagrant
Vagrant is a toll for building development environments.

###Folders to look at:
There is one main folder - The DevEnvironemnts folder which contains:
- environment (folder)
- app (folder)
- Vagrantfile (file)

###Tools needed
- Virtual box
- Terminal
- Atom

###Getting Started
1. Open terminal and using `cd` navigate to the location of the folder DevEnvironemnts.
2. type `vagrant up`. This will download ubuntu/xenial64 (specified in VagrantFile). if you open the VagrantFile you should see this:
`Vagrant.configure("2") do |config|
  config.vm.box ="ubuntu/xenial64"`
- Now the vm is running.
3. Type `vagrant ssh`. This command will connect you to the VM using SSH.
4. If you open the VirtualBox application you will see the VM running.
5. Type in `192.168.10.100` to see the machine via your browser.
 - if you cannot access this, type `sudo systemctm restart nginx` in your terminal and then start up the vm again.

- If nothing is working, you will need to install some packages.
  - first navigate to environments folder using `cd environments` (via DevEnvironmets).
  - type in `cd spec-tests` then type `rake spec`. this will display all the packages that need to be installed.
  - `cd ..` takes you back to DevEnvironmets folder. type in `vagrant destroy` to destroy any existing vm's.
  - type `vagrant up`. this runs the vm and installs packages using code from provision.sh
  - navigate to spec-tests folder. type `rake spec`. you will see that the packages are being installed.
