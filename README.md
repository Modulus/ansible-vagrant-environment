# What is this
Local vagrant test environment with x amount of machines. You must have ansible on your local machine

# SSH access
ssh-add ~/id_rsa.pub

# Create machines
vagrant up 


# Run ansible to check nodes
ansible -i inventories/vagrant nodes -m ping

You can omit the -i resulting in
ansible nodes -m ping

# Run test playbook
ansible-playbook rollout_user.yml

Knock your socks of. Play around!