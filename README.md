Tony's Personal Ansible Repo
===================

Introduction
-----------
This repo is a dumping ground for my personal Ansible playbooks.  I
have written several playbooks for building out environments on virtual
machines.  Most of these virtual machines are used for doing data
analytics for science and engineering or for building automated
trading systems.

The playbooks are fairly simple and straightforward.  I typically
will keep environment build-out playbooks contained in one YAML file
as opposed to using the Ansible developer's suggested [directory
structures](http://docs.ansible.com/ansible/playbooks_best_practices.html#directory-layout).  I do this for the sake of simplicity. 

Also, I do not have any inventory files located within this repo.
That should be pretty self explanatory as to why I do not do this.

Feel free to use any of these, but use them at your own risk.
Probably best to think of these as examples to build your own
playbooks as I am sure the version numbers of the specific
applications may not be what you want them to be.


Contents
--------

### Algorithmic Trading Research Dekstop

#### Description
Ansible Playbook for configuring a (L)ubuntu desktop environment to be
used for Algorithmic Trading Research.  This is based off of the
awesome educational program put together by Michael Halls-Moore at [QuantStart](https://www.quantstart.com/)

#### Examples

##### Execute the Ansible Playbook
This assumes of course, that you have an inventory file name 'hosts'
and that you have setup SSH public key authentication setup between
your ansible client environment and the host(s) your trying to connect
to.  You will need to replace my username "tmendoza" with the user
name of the id connecting to the host(s) in your inventory file.

```Shell Session
$ ansible-playbook -u tmendoza -b -K --become-user=root
--become-method=sudo -i hosts -v algorithmic-trading-research-ubuntu-17.04.yml
```

#### Currently Supported Ubuntu OS Release:

Distributor ID:	Ubuntu
Description:	Ubuntu 17.04
Release:	17.04
Codename:	zesty

#### References
* https://www.quantstart.com/articles/Installing-a-Desktop-Algorithmic-Trading-Research-Environment-using-Ubuntu-Linux-and-Python
* https://www.quantstart.com/articles/Securities-Master-Database-with-MySQL-and-Python

#### Notes
This playbook only installs the basic packages and python libraries
needed.  It does not do the actual configuration.  That will be coming
in the next release of this Playbook.

#### Todo
* Create a Vagrant configuration which uses this playbook
* Create tests for each one of the package installs
* Create and install some MariaDB templates for the [Securities Master Database](https://www.quantstart.com/articles/Securities-Master-Database-with-MySQL-and-Python)

**Author:** Tony Mendoza

