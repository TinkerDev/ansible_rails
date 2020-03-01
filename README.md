### Ansible roles and example playbook to configure server for rails app 

## Install ansible
    brew install ansible
  
## Create Configuration files 
Copy hosts file with list of alias-ip of servers you want to configure

    cp hosts_example hosts    
  
Copy per-host configuration files
    
    cp host_vars_example host_vars
    
## Configure that files    

## Go add your ssh public key to server /home/root/.ssh/authorized_keys

## Run ansible playbook
Use default roles from playbook

    ansible-playbook playbook.yml -i hosts --limit=myserver

Or select that you need

    ansible-playbook playbook.yml -i hosts -t dependencies,ruby,postgres,nginx --limit=myserver

List of roles:
  - dependencies
  - ruby
  - postgres
  - nginx
  - node
  - redis
  
  
## You also need in your capfile

    require "capistrano/rbenv"    
    require "capistrano/bundler"
    require "capistrano/rails"    
    require "capistrano/puma"
    install_plugin Capistrano::Puma
    require "capistrano/sidekiq"
    require "whenever/capistrano"
    require 'capistrano-db-tasks'    