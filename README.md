This software is released under the MIT License, see LICENSE.txt.

[日本語版](https://github.com/yukihirai0505/centos-6.7-ansible/blob/master/README_ja.md)

## About

Ansible for CentOS6.7

- PHP7
- Nginx
- MySQL5.6
- Java1.8
- Python3.5
- cron
- supervisor

etc

## Get Started

Using this Vagrantfile in this project

[https://github.com/yukihirai0505/centos-6.7-ansible/blob/master/Vagrantfile](https://github.com/yukihirai0505/centos-6.7-ansible/blob/master/Vagrantfile)

If you haven't installed ansible

`pip install ansible`

And then

- `vagrant up` 

- `vagrant ssh-config --host centos-6.7 >> ~/.ssh/config`

**If you can't use ssh, you may need to save private_key**

```
ssh-keygen -yf .vagrant/machines/default/virtualbox/private_key > public_key
cat public_key | pbcopy
```

And then save CentOS6.7 `~/.ssh/authorized_keys` file

`sudo chmod 600 ~/.ssh/authorized_keys` 


【Reference】

- ["Warning: Authentication failure. Retrying... " after packaging box](https://github.com/mitchellh/vagrant/issues/5186)

After that,
make hosts file to following path

`/etc/ansible/hosts`

```
[host]
centos-6.7
```

finally, you can ansible-playbook

`ansible-playbook development.yml`