docker
======

Configure Docker as per the [official instructions](https://docs.docker.com/installation/ubuntulinux/#ubuntu-trusty-1404-lts-64-bit),
using the Docker provided repository.

Requirements
------------

Tested on:

* Ubuntu 14.04 LTS

Role Variables
--------------

* docker_users

List of users to add to the docker group, granting them control of Docker.
Defaults to an *empty list* ('[]')

* docker_enable_memory_accounting

Whether to enable memory and swap accounting. Defaults to *false*. Enabling will
cause the server to be rebooted to affect kernel parameter changes.

* docker_ssh_port

Port used to test server for server reboot completing. Defaults to *22*, but
really uses *ansible_ssh_port* and will only use this value if that isn't set.

* docker_remote_clients

List of remote IP addresses to allow access via UFW to the server. Defaults to
*undefined*. Note that ufw is not started or enabled by this module.

Dependencies
------------

None

Example Playbook
----------------

```yaml
    - hosts: servers
      roles:
         - { role: willshersystems.docker,
           docker_enable_memory_accounting: true }
```

License
-------

LGPLv3

Author Information
------------------

Matt Willsher, matt@willsher.systems
