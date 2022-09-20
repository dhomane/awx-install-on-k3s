# awx-install-on-k3s
Install AWX on k3s


Automated deployment of single node k3s cluster running AWX

Requirements
------------

Ubuntu 20.04/22.04

Cent0S 8 Stream

4 GB RAM

2 CPU

Role Variables
--------------

**k3s_version**: The k3s release to deploy, default is v1.25.0+k3s1

**operator_version:** The awx operator release, default 0.29.0

**awx_version**: AWX release, default 21.6.0

**awx_admin_password**: Set admin password for web interface

**postgres_password:** Set database password, default "mydbpasswd"

**awx_hostname**: Set web address, default "my.awx.home"

Example Playbook
----------------

1. deploy.yml can be used to execute against an inventory

```
ansible-playbook -i YourInventoryFile deploy.yml

```
2. If using ansible-navigator with the config included in his repo,
   antuelle78/awx-ee:2.13.4 EE image is used and the container is launched on
   the host network.

```
ansible-navigator run deploy.yml -i YourInventoryFile

```

3. Add "-m stdout" to replicate ansible-playbook behaviour when using
   ansible-navigator

```
ansible-navigator run deploy.yml -i YourInventoryFile -m stdout

```

4. Add "--skip-tags=k3s_install" to bypass reinstalling k3s on subsequent runs.

```
ansible-navigator run deploy.yml -i YourInventoryFile --skip-tags=k3s_install

```

5. This repo can also be imported into an existing AWX/Tower instance as a project

**Ansible Navigator Documentation:**

https://ansible-navigator.readthedocs.io/en/latest/


Access AWX Web Interface
----------------

Visit http://my.awx.home after successful deployment when using default values.


license
-------

GPLv3

Author Information
------------------

Name: Michael Nelson

LET'S GET IT AUTOMATED AND BE LAZY :<)
