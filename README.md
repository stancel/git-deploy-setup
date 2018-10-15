git-deploy-setup
=========

Ansible role that sets up a git bare repository and git working tree directory so that a git repo can be pushed to deploy onto a web server.

Requirements
------------

You'll want to already have some sort of webserver setup (Apache, NginX, etc.).

Role Variables
--------------

The domain of the site to receive the Git post-receive hook. This is a required variable.
```
	git_deploy_setup_domain: "somesite.com"
```
The document root for the webserver. The default is set as "/var/www".
```
	git_deploy_setup_web_home: "/var/www"
```

The folder inside the web_home document root that stores the files served up by the webserver for this site. The default is set as "/html".

```
	git_deploy_setup_web_folder: "/html"
```

The file path on the server for setting up the git bare repo. The default is "/var/git".  
```
	git_deploy_setup_git_home: "/var/git"
```

Whether or not this git deployment setup should be run
```
	git_deploy_setup_git_create: True
```

The linux username used by your webserver. The default value is "www-data" which assumes Apache is used on a Debian or Ubuntu linux.
```
	git_deploy_setup_web_user: "www-data"
```

The linux group used by your webserver. The default value is "www-data" which assumes Apache is used on a Debian or Ubuntu linux.
```
	git_deploy_setup_web_group: "www-data"
```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

	- hosts: your_server
	  vars_files:
	    - vars/main.yml
	  roles:
	    - stancel.git-deploy-setup 

or just pass the variables in the playbook

	- hosts: your_server 
	  vars:
		git_deploy_setup_domain: "somesite.com"
	  roles:
	    - stancel.git-deploy-setup


License
-------

GPLv3

Author Information
------------------

[Brad Stancel](https://github.com/stancel) 


