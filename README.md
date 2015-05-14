### This is a group of ansible roles that I use


Copy example hosts file into real one and edit it after

    cp hosts_example hosts
    cp host_vars_example host_vars

Use default roles from playbook

    ansible-playbook playbook.yml -i hosts --limit=jumper

Or select that you need

     ansible-playbook playbook.yml -i hosts -t dependencies,ruby,postgres,nginx --limit=jumper

List of roles:
  - dependencies
  - ruby
  - postgres
  - nginx
  - bower