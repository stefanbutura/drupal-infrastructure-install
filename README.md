# Provision infrastructure for Drupal servers

## How to use this repo locally

1. Clone the repository
2. Install dependencies: `ansible-galaxy install -r requirements.yml`
3. Copy host_vars/1.2.3.4 -> host_vars/aaa.bbb.ccc.ddd and edit according to your needs
4. Provision a single host: `/run.sh -l aaa.bbb.ccc.ddd`

## What the playbook does

- Installs git
- Installs nginx and creates virtual hosts
- Installs certbot and creates certificates for the virtual hosts, adds cronjobs to automatically renew those
- Installs MySQL and creates databases
- Installs PHP (PHP-FPM)
- Creates SSH users based on Github accounts (SSH keys retrieved from https://github.com/USERNAME.keys)
- Create the "web" user that should be used for Drupal deployments
- Creates the /var/www/config/domain.com folders, with all the settings files 
- Creates the /var/www/artifacts folder for Github actions
- Creates crontab entries that run drush:cron for each site

## What's left to do after this

- Import a database dump
- Do an usual Github Actions deployment
