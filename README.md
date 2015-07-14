# # Ansible Piwik Example with Vagrant

This is a example of Piwik deployment of ansible provisioned by Vagrant.

# Requirements

To bring up the Vagrant environment, it requires the followings to be install on your host machine:

1. Ansible (tested with 1.9.2)
2. sshpass (tested with 1.0.5)
3. Vagrant (tested with 1.7.2)

# Piwik explanation

There are a virtual machines defined in this stack:

| Hostname | IP | CPU | Memory | Role |
| ---------- | ---------- | ---------- | ---------- | ---------- |
| piwik  | 10.10.10.10  | 4 | 512 MB | nginx + php + mysql + piwik |

# Bring up the piwik

Run the command:

```shell
$ vagrant up
```

When finished, you should be able access `piwik` from http://10.10.10.10 .

If you make changes in the playbook, run:

```
$ vagrant provision
```
