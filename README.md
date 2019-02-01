# What is this
Local vagrant test environment with x amount of machines. You must have ansible on your local machine. This project has example for a simple playbook and role. Expand this as you wish.

Pull requests are welcome

# Install python requirements
This is ansible and testinfra for the sample tests.

pip install -r requirements.txt

# SSH access
ssh-add ~/id_rsa.pub

# Create machines
vagrant up 


# Run ansible to check nodes
ansible -i inventories/vagrant nodes -m ping

You can omit the -i resulting in
ansible nodes -m ping

# Run test playbook
ansible-playbook playbook.yml

Knock your socks of. Play around!

## To run tests
py.test tests --hosts="ansible://nodes" --ansible-inventory="inventories/vagrant"

**To test spesific test run:**
py.test tests/test_verify_user.py --hosts="ansible://nodes" --ansible-inventory="inventories/vagrant"