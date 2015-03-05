# RoadMap for CIBOX

1. Add support for CentOS, possibly OpenBSD/FreeBSD
2. Add GUI for ability to run playbook via web UI (SaaS)
3. Test VPSDIME hosting provider

## Cleanup Issue queue

### Bugs
* [JSHINT fixes](https://github.com/propeoplemd/cibox/issues/84)

### Performance
* [MYSQL tmpdir to ram](https://github.com/propeoplemd/cibox/issues/5)
* [MYSQL caches options](https://github.com/propeoplemd/cibox/issues/57)
* [MYSQL limits options](https://github.com/propeoplemd/cibox/issues/58)
* [fstab optimizations](https://github.com/propeoplemd/cibox/issues/23)
* [SetUp proper opcode cacher](https://github.com/propeoplemd/cibox/issues/7)

### Security
* [Add htpasswd protection](https://github.com/propeoplemd/cibox/issues/70)
* [Default permissions](https://github.com/propeoplemd/cibox/issues/73)
* [Security scanners](https://github.com/propeoplemd/cibox/issues/93)
* [Puppet ssh key fix](https://github.com/propeoplemd/cibox/issues/94)

### QA
* [CodeSniffer skip array of rules](https://github.com/propeoplemd/cibox/issues/36)
* [Convert configs to templates](https://github.com/propeoplemd/cibox/issues/14)
* [Windows users docs](https://github.com/propeoplemd/cibox/issues/11)
* [Investigate and integrate sonarqube code checker](https://github.com/propeoplemd/cibox/issues/9)
* [Add cs-fixer to cibox](https://github.com/propeoplemd/cibox/issues/44)

### Features
* [Add environment variables](https://github.com/propeoplemd/cibox/issues/95)
* [rename drupal folder to docroot (Acquia)](https://github.com/propeoplemd/cibox/issues/92)
* [Per build subdomain feature](https://github.com/propeoplemd/cibox/issues/74)
* [preconfigure xdebug](https://github.com/propeoplemd/cibox/issues/67)
* [Redis vs memcached](https://github.com/propeoplemd/cibox/issues/33)
* [Initial memcached installation](https://github.com/propeoplemd/cibox/issues/26)
* [Implement https for ci and vm boxes](https://github.com/propeoplemd/cibox/issues/34)
* [Add nginx as option](https://github.com/propeoplemd/cibox/issues/35)
* [Integrate D8 support from past codesprint](https://github.com/propeoplemd/cibox/issues/39)
* [Backport NAS,SJ,TFALL stuff to cibox](https://github.com/propeoplemd/cibox/issues/45)
* [Backport NAS features](https://github.com/propeoplemd/cibox/issues/83)
* [Enpower CIBOX's repo with own jenkins builder](https://github.com/propeoplemd/cibox/issues/51)
* [Integrate munin|logstash within cibox](https://github.com/propeoplemd/cibox/issues/53)
* [Migrate to ansible from puppet](https://github.com/propeoplemd/cibox/issues/71)
* [Create ansible role for mysql file_per_table migration](https://github.com/propeoplemd/cibox/issues/76)
* [Install mailcatcher](https://github.com/propeoplemd/cibox/issues/82)