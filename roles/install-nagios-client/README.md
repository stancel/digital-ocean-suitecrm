install-nagios-client
=========

A role to install the Nagios NRPE client onto an Ubuntu/Debian machine and open up the required firewall ports (5666) in ufw (if used) to allow communication with the Nagios Server.

Requirements
------------

You should be running your own Nagios, Icinga2 or other Nagios plugin compatible server.

Role Variables
--------------

Fully qualified domain name of your Nagios Server
```
	nagios_server_fqdn: "mynagios.mydomain.com"
```
The fully qualified domain name or IP address of the machine you are adding to be monitored
```
	server_fqdn: "myserver-to-monitor.com"
```

Dependencies
------------

None

Example Playbook
----------------


	- hosts: your_server_to_monitor
	  vars_files:
	    - vars/main.yml
	  roles:
	    - { role: stancel.install-nagios-client }


or 

	- hosts: your_server_to_monitor
	  vars:
		nagios_server_fqdn: "nagios.mydomain.com"
		server_fqdn: "myserver-to-monitor.com"
	  roles:
	    - { role: stancel.install-nagios-client }

License
-------

BSD

Author Information
------------------

Brad Stancel
