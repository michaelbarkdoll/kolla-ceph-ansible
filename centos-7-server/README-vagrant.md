# To boot the cluster with vagrant

```
vagrant up

# Prep Ceph nodes ceph-bootstrap-nodes.yml
vagrant provision --provision-with ansible-ceph-prep
# ansible-playbook -i staging ceph-bootstrap-nodes.yml

# Deploy Ceph 
# ansible-playbook -i staging ceph-deploy-playbook.yml
# vagrant provision --provision-with ansible-ceph-deploy

# OpenStack BootStrap the nodes runs os-bootstrap-nodes.yml
vagrant provision --provision-with ansible
# ansible-playbook -i staging os-bootstrap-nodes.yml

# Deploy OpenStack os-bootstrap-deploy-nodes.yml
vagrant provision --provision-with ansible-os-deploy
# ansible-playbook -i staging os-bootstrap-deploy-nodes.yml
```

# Destroy the vagrant cluster
```
vagrant destroy -f
```