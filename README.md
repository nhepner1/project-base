Project Base
============

Project base is a Vagrant/Ansible configuration and is set up to provide a quick 
LAMP stack environment for development. This is to provide a rapid, generic 
development environment to increase stability and reduce ramp-up time for projects.

Primarily, this has been used to instance quick drupal sites with a full database 
and server stack, as well as a few PECL dependencies, however, it can be used to 
work on any LAMP project. This automates a lot of tasks, and while some of the 
downloads might take a little while, actual personal involvement before being able 
to develop is about 5 minutes.

Requirements
------------
This installation should work for all major flavors of linux, and 
OSX. On Windows, Vagrant >= 1.8.2 is required. 

 * Vagrant  >1.8.2 [Install](https://docs.vagrantup.com/v2/installation/index.html)
 * Virtualbox [Download and install](https://www.virtualbox.org/wiki/Downloads)
 * Ansible [Install](https://docs.ansible.com/ansible/intro_installation.html#installing-the-control-machine)
 
#### Hostmanager (Optional)
Install the vagrant hostmanager plugin
```
vagrant plugin install vagrant-hostmanager
```

Usage
-----
Checkout the project-base to your local machine. Rename it to whatever your project is.
```
git clone git@github.com:nhepner1/project-base.git ./myproject
```

Change directories into the 'myproject' folder
```
cd myproject
```

This project is set to sync to the project/docroot directory. If this directory does not exist 
within the project, the build will fail.

---------
##### If your project already has a docroot folder #####

Clone your project into the current folder. Rename the cloned project as "project"
```
git clone git@github.com:myrepo/myproject.git ./project
```

##### If your project does not have a docroot folder #####

Create the project directory and change into it.
```
mkdir project
cd project
```

Clone your project into the docroot folder
```
git clone git@github.com:myrepo/myproject.git ./docroot
```

Change directories back to the project root folder
```
cd ../
```
---------

Instance Vagrant
```
vagrant up
```

---------

##### If Hostmanager is installed #####
Use vagrant's hostmanager plugin to add the site name and IP address to the /etc/hosts file.
```
vagrant hostmanager
```

##### If Hostmanager not installed #####
Add the IP and hostname to the /etc/hosts file manually
```
sudo echo '192.168.33.10 vagrant.dev' >> /etc/hosts
```
---------

Navigate to 'http://vagrant.dev' in your browser of choice.

Develop your site within the project/docroot folder using the tools of choice on your host 
machine. Have fun!

Credentials
-----------
MySQL Database: drupal
MySQL User: drupal_user
MySQL Password: drupaldbpass

Current Project Status
----------------------
While this project is under active development, it is **not** expected to hit a 1.0 release
unless significant interest is demonstrated.

Most development changes will be added as needed by myself or my web development students on
an as-needed basis. 

Pull requests are welcome, and will be reviewed and added.

Contributing
------------
Anyone is encouraged to contribute to the project by 
[forking](https://help.github.com/articles/fork-a-repo) and submitting a pull 
request. (If you are new to GitHub, you might start with a 
[basic tutorial](https://help.github.com/articles/set-up-git)).

By contributing to this project, you grant a world-wide, royalty-free, perpetual, 
irrevocable, non-exclusive, transferable license to all users under the terms of 
the Gnu General Public License v2 or later.

All comments, messages, pull requests, and other submissions received through this Github
page are subject to moderation by Nick Hepner, a representative thereof, or 
Github, per the terms of the Github user agreement.

Support
-------
No support is offered or implied with this code base, however, it is ENCOURAGED
to engage in discussion or create tickets within the [github issue queue
associated with this project](https://github.com/nhepner1/project-base/issues). 
Please tag discussions with the 'discussion' and other tickets appropriately.

It is also highly encouraged to undertake solutions for tickets that have already 
been created.

License
-------
The project utilizes code licensed under the terms of the GNU General Public License
and therefore is licensed under GPL v3 or later.

This program is free software: you can redistribute it and/or modify it under the 
terms of the GNU General Public License as published by the Free Software Foundation, 
either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY 
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A 
PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this 
program. If not, see http://www.gnu.org/licenses/.