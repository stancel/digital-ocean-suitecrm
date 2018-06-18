add-config-to-nagios-server
=========

Basic Ansible role to add a server to be monitored by Nagios. Defines services for SSH, Ping, MySQL and HTTP

Requirements
------------

Assumes that your Nagios Server is installed in the following path `/usr/local/nagios`

Role Variables
--------------

The hostname of the machine you are monitoring. Host names should not have spaces in them.
```
	host_name: "my-server"   
```
The alias or Nagios friendly name to show in Nagios as the computer being monitored
```
	nagios_friendly_name: "My Important Server"
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

	- hosts: your_nagios_server
	  vars_files:
	    - vars/main.yml
	  roles:
	    - { role: stancel.add-config-to-nagios-server }


or 

	- hosts: your_nagios_server
	  vars:
		host_name: "my-server"
		nagios_friendly_name: "My Important Server"
		server_fqdn: "myserver-to-monitor.com"
	  roles:
	    - stancel.add-config-to-nagios-server 

License
-------

GPLv3

Author Information
------------------

Brad Stancel