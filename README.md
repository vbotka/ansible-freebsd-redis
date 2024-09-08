# freebsd_redis

[![quality](https://img.shields.io/ansible/quality/27910)](https://galaxy.ansible.com/vbotka/freebsd_redis)
[![Build Status](https://app.travis-ci.com/vbotka/ansible-freebsd-redis.svg?branch=master)](https://ap.travis-ci.com/vbotka/ansible-freebsd-redis)
[![GitHub tag](https://img.shields.io/github/v/tag/vbotka/ansible-freebsd-redis)](https://github.com/vbotka/ansible-freebsd-redis/tags)

[Ansible role.](https://galaxy.ansible.com/vbotka/freebsd_redis/) FreeBSD. Install and configure Redis.

Feel free to [share your feedback and report issues](https://github.com/vbotka/ansible-freebsd-redis/issues).

[Contributions are welcome](https://github.com/firstcontributions/first-contributions).


## Requirements

### Packages

* FreeBSD package or port databases/redis

### Collections

* community.general


## Role Variables

See defaults and examples in vars.


## Workflow

* Change shell on the remote host to /bin/sh if necessary

```bash
shell> ansible dbserver -e 'ansible_shell_type=csh ansible_shell_executable=/bin/csh' -a 'sudo pw usermod freebsd -s /bin/sh'
```

* Install the role and collections

```bash
shell> ansible-galaxy role install vbotka.freebsd_redis
```

Install the collection if necessary

```bash
shell> ansible-galaxy collection install community.general
```

* Create playbook and inventory

```bash
shell> cat redis.yml

- hosts: dbserver
  roles:
    - vbotka.freebsd_redis
```

```bash
shell> cat hosts
[dbserver]
<SERVER1-IP-OR-FQDN>
<SERVER2-IP-OR-FQDN>
[dbserver:vars]
ansible_connection=ssh
ansible_user=freebsd
ansible_python_interpreter=/usr/local/bin/python3.9
ansible_perl_interpreter=/usr/local/bin/perl
```
		
* Check syntax

```bash
shell> ansible-playbook redis.yml --syntax-check
```

* Fit variables to your needs.

* Display variables

```bash
shell> ansible-playbook redis.yml -t bsd_redis_debug -e bsd_redis_debug=true
```

* Install Redis

```bash
shell> ansible-playbook redis.yml -t bsd_redis_pkg -e bsd_redis_install=true
```
		
* Dry-run the play and display differences

```bash
shell> ansible-playbook redis.yml --check --diff
```

* Configure Redis

```bash
shell> ansible-playbook redis.yml
```

## Troubleshooting

See the log at the remote host

```bash
shell> tail -f /var/log/redis/redis.log
```

## Ansible lint

Use the configuration file *.ansible-lint.local* when running
*ansible-lint*. Some rules might be disabled and some warnings might
be ignored. See the notes in the configuration file.

```bash
shell> ansible-lint -c .ansible-lint.local
```


## References

- [Redis Quick Start](https://redis.io/topics/quickstart/)
- [Redis Configuration](https://redis.io/topics/config/)
- [Redis](https://redis.io/)
- [RedisLabs](https://redislabs.com/)


## License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


## Author Information

[Vladimir Botka](https://botka.info)
