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

Once deploy machine has finished, you can shut it down to save host resources

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

Modify /opt/elastic/elasticsearch.yml

```
**** ToDo  changes here  ****
```

Edit /etc/security/limits.conf as sudo

```
#<domain>    <type>   <item>   <value>
vagrant    soft    nofile   65536
vagrant    hard    nofile   65536
vagrant    soft    nproc    4096
vagrant    hard    nproc    4096
```

Start elasticsearch again

/opt/elastic/elasticsearch-6.4.2/bin/elasticsearch






