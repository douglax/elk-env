#### Clone the repo into local filesystem

```
git clone https://github.com/gmlp/elk-env 
```

#### Bring the virtual machines uo

```
vagrant up
```

#### ssh into deployment machine

```
vagrant ssh deploy
```

#### Run the ansible playbooks that will install the ELK tools

```
ansible-playbook /vagrant/ansible
```

#### Repeat the previous step in es-cluster-node-1 vagrant machine

This can be performed in other terminal for practical purposes

```
vagrant ssh es-cluster-node-1
ansible-playbook /vagrant/ansible
```

```
vagrant halt deploy
```

#### Configure es-cluster-node 1


cd to installation directory to review and change configuration

cd /opt

Edit jvm.options

Change heap memory to half of the available memory in vagrant machine (from 1g to 512M)

-Xms512m
-Xmx512m



