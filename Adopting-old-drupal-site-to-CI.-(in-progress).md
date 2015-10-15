There are projects, when there is already working site, based on Drupal.
And there is no way to work with profile flow for the site, at least in terms of fast development.
So the only option is SQL flow, but there are steps you should follow to get success.

1. Prepare latest database dump from origin site. This can be done periodically via Jenkins job for obtaining latest results into development process during it.
For storing database use ```/var/www/backup``` folder and put the name from global_settings.yml

```yml
# htpasswd protection for securing backups.
backup_user: propeople
backup_pass: givemebackup
# Source backup database that will be downloaded to build site.
# In many cases this is production dump.
source_backup_name: latest_prod.sql.gz
# URL to the source database. Can be overridden by CI server.
source_database: http://{{ backup_user }}:{{ backup_pass }}@192.168.56.132/backup/{{ source_backup_name }}
```
Change source_database variable accordinly 