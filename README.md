freebsd_redis
=============

[![Build Status](https://travis-ci.org/vbotka/ansible-freebsd-redis.svg?branch=master)](https://travis-ci.org/vbotka/ansible-freebsd-redis)

[Ansible role.](https://galaxy.ansible.com/vbotka/freebsd_redis/) FreeBSD. Install and configure Redis.


Requirements
------------

No requiremenst.


Variables
---------

TBD. Review defaults and examples in vars.


Workflow
--------

1) Change shell to /bin/sh.

```
# ansible dbserver -e 'ansible_shell_type=csh ansible_shell_executable=/bin/csh' -a 'sudo pw usermod freebsd -s /bin/sh'
```

2) Install role.

```
# ansible-galaxy install vbotka.freebsd_redis
```

3) Fit variables.

```
# editor vbotka.freebsd_redis/vars/main.yml
```

4) Create playbook and inventory.

```
# cat redis.yml

- hosts: dbserver
  roles:
    - vbotka.freebsd_redis
```

```
# cat hosts
[dbserver]
<SERVER1-IP-OR-FQDN>
<SERVER2-IP-OR-FQDN>
[dbserver:vars]
ansible_connection=ssh
ansible_user=freebsd
ansible_python_interpreter=/usr/local/bin/python3.6
ansible_perl_interpreter=/usr/local/bin/perl
```

5) Install and configure redis.

```
# ansible-playbook redis.yml
```
		

References
----------

- [Redis Quick Start](https://redis.io/topics/quickstart/)
- [Redis Configuration](https://redis.io/topics/config/)
- [Redis](https://redis.io/)
- [RedisLabs](https://redislabs.com/)

License
-------

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


Author Information
------------------

[Vladimir Botka](https://botka.link)
