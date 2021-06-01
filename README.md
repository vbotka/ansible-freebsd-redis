# freebsd_redis

[![quality](https://img.shields.io/ansible/quality/27910)](https://galaxy.ansible.com/vbotka/freebsd_redis)[![Build Status](https://travis-ci.org/vbotka/ansible-freebsd-redis.svg?branch=master)](https://travis-ci.org/vbotka/ansible-freebsd-redis)

[Ansible role.](https://galaxy.ansible.com/vbotka/freebsd_redis/) FreeBSD. Install and configure Redis.

Feel free to [share your feedback and report issues](https://github.com/vbotka/ansible-freebsd-redis/issues).

[Contributions are welcome](https://github.com/firstcontributions/first-contributions).


## Requirements

### Collections

- community.general


## Variables

Review defaults and examples in vars.


## Workflow

1) Change shell to /bin/sh.

```
shell> ansible dbserver -e 'ansible_shell_type=csh ansible_shell_executable=/bin/csh' -a 'sudo pw usermod freebsd -s /bin/sh'
```

2) Install the role and collections

```
shell> ansible-galaxy role install vbotka.freebsd_redis
shell> ansible-galaxy collection install community.general
```

3) Fit variables, e.g. in vars/main.yml

```
shell> editor vbotka.freebsd_redis/vars/main.yml
```

4) Create playbook and inventory

```
shell> cat redis.yml

- hosts: dbserver
  roles:
    - vbotka.freebsd_redis
```

```
shell> cat hosts
[dbserver]
<SERVER1-IP-OR-FQDN>
<SERVER2-IP-OR-FQDN>
[dbserver:vars]
ansible_connection=ssh
ansible_user=freebsd
ansible_python_interpreter=/usr/local/bin/python3.7
ansible_perl_interpreter=/usr/local/bin/perl
```

5) Install Redis

```
shell> ansible-playbook redis.yml -t bsd_redis_packages
```
		
6) Check the playbook

```
shell> ansible-playbook redis.yml --syntax-check
shell> ansible-playbook redis.yml --check --diff
```

7) Configure Redis

```
shell> ansible-playbook redis.yml
```


## References

- [Redis Quick Start](https://redis.io/topics/quickstart/)
- [Redis Configuration](https://redis.io/topics/config/)
- [Redis](https://redis.io/)
- [RedisLabs](https://redislabs.com/)


## License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


## Author Information

[Vladimir Botka](https://botka.link)
