# pi-swarm-ansible

Docker swarm installation and set up among pi
Ansible playbook that allow to install docker(+swarm) and set up a cluster on rpi (and non arm arch).


## Inventory
5 roles exist for theses playbooks:
nodes (list here every node), managers (docker swarm managers), workers (docker swarm worker) and
nodes-arm, node-ubuntu (for custom docker installation).


## Usage
3 playbooks are available to setup, deploy and delete a swarm cluster.

### Setup
Install docker swarm on every nodes
-K is mandatory to have root permission for package installation.
```
ansible-playbook -i inventory.ini -u pi cluster-setup.yml -K
```
### Deploy the cluster
Create the cluster with the roles chosen in the invetory file.
```
ansible-playbook -i inventory.ini -u pi cluster.yml         
```
### Delete the cluster

Remove every node from the swarm cluster
```
ansible-playbook -i inventory.ini -u pi delete-cluster.yml  
```
