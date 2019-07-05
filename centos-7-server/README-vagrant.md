# To boot the cluster with vagrant

```
vagrant up

# Bootstrap nodes (must use ansible)
# vagrant provision --provision-with bootstrap
ansible-playbook -i staging bootstrap-nodes.yml


# Prep Ceph nodes ceph-bootstrap-nodes.yml
# vagrant provision --provision-with ansible-ceph-prep
ansible-playbook -i staging ceph-bootstrap-nodes.yml

# Deploy External Ceph (optionally, skip if internal ceph)
# vagrant provision --provision-with ansible-ceph-deploy
ansible-playbook -i staging ceph-deploy-playbook.yml

# OpenStack BootStrap the nodes runs os-bootstrap-nodes.yml
# vagrant provision --provision-with ansible
ansible-playbook -i staging os-bootstrap-nodes.yml

# Deploy OpenStack os-bootstrap-deploy-nodes.yml
# vagrant provision --provision-with ansible-os-deploy
ansible-playbook -i staging os-bootstrap-deploy-nodes.yml
```

```
vagrant up && vagrant provision --provision-with ansible-ceph-prep && vagrant provision --provision-with ansible
```

```
vagrant up && ansible-playbook -i staging ceph-bootstrap-nodes.yml && ansible-playbook -i staging os-bootstrap-nodes.yml && ansible-playbook -i staging os-bootstrap-deploy-nodes.yml
```

All-in-one
```
vagrant up && ansible-playbook -i staging ceph-bootstrap-nodes.yml && ansible-playbook -i staging os-bootstrap-nodes.yml && ansible-playbook -i staging os-bootstrap-deploy-nodes.yml
```

```
vagrant provision --provision-with ansible-ceph-prep && vagrant provision --provision-with ansible && vagrant provision --provision-with ansible-os-deploy
```

# Destroy the vagrant cluster
```
vagrant destroy -f
```