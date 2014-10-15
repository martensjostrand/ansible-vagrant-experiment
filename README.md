# My Ansible and Vagrant experiment #

## How to run ##
Install Ansible, Vagrant and VirualBox:

```
$ansible --version
ansible 1.5

$ vagrant --version
Vagrant 1.6.5

$ VBoxManage --version
4.3.16r95972
```

Create VMs and provision by:
```
$ vagrant up
```

## What you get ##
- HTTP service running at http://192.168.100.10/
- Two loadbalancers
  - Slave at http://192.168.100.100/ with statistics at http://192.168.100.100:8080/stats, login user:pwd
  - Master at http://192.168.100.101/ with statistics at http://192.168.100.101:8080/stats, login user:pwd
- Webbfronts
  - http://192.168.100.110/
  - http://192.168.100.111/
