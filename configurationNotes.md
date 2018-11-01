### Clone the repo into local filesystem

```
git clone https://github.com/gmlp/elk-env 
```

### Bring the virtual machines uo

```
vagrant up
```

### ssh into deployment machine

```
vagrant ssh deploy
```

### Run the ansible playbooks that will install the ELK tools

```
ansible-playbook /vagrant/ansible
```



