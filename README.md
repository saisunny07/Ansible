For Ansible to access target machines, password less authentication must be enabled to access target machines. This can be done by setting up Server machine as known host in all the target machines.

Setting Server Machine as Known Host:

STEP 1:

- Generate an ssh key on server using the command ssh-keygen.

- A .ssh folder is created, which consists on public key, copy it.


STEP 2:

- Generate an ssh key all the Targets.

- In the .ssh folder navigate to the known_hosts and add the the Server ssh public key.

Now Server can access the Target without any password.


STEP 3:

- Create an inventory file, a file that contains the IP addresses of the target machines.
  
  Ex: inventory

STEP 4: Ansible commands
    ansible -i inventory all -m 'shell' -a 'ls'

The above command displays the files on all the target machines. -m => module, -a => argument. We can all also make changes only to the specified target machines by replacing 'all' in the command with [Group_Name] of the inventory file.


    ansible-playbook -i inventory yml_file
  Ex: first_playbook.yml







