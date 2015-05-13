### This is a group of ansible recipes we use in out projects


Copy example hosts file into real one, edit it after

    cp hosts_example hosts


Use default roles from playbook

    ansible-playbook playbook.yml -i hosts --limit=jumper

Or use specific roles

     ansible-playbook playbook.yml -i hosts -t ruby,deploy,postgresql,nginx --limit=jumper

List of roles:
  - nginx

