digital-ocean-suitecrm
=========

Ansible playbook to create and provision a server on DigitalOcean in order to run the SuiteCRM software.


How to Use
------------

To use this playbook just run this command.

	1. ansible-galaxy install -r requirements.yml -p roles/  
	2. Create a file called .vault_pass in this folder and put a random string in it for decrypting your sensitive variables. Something like: QSkngTv#KTJ=WXpg6qVR
	3. Fill out needed variables in vars/all_vars.yml and vars/vault.yml files
	4. ansible-vault encrypt vars/vault.yml   #Encrypt the sensitive variables
	5. ansible-playbook master.yml -e @vars/all_vars.yml -e @vars/vault.yml -i /Users/Brad/.ansible/hosts


Requirements
------------

None

Variables
------------

See the `vars/all_vars.yml` and `var/vault.yml` files for all of the needed variable values to fill out.


Roles
------------

	- stancel.create-digitalocean-droplet
	- stancel.apache-webserver
	- tersmitten.percona-server
	- stancel.setup-mysql-backups
	- stancel.install-bareos-client
	- stancel.add-job-to-bareos-director
	- stancel.install-nagios-client
	- stancel.add-config-to-nagios-server
	- stancel.git-download-suitecrm

