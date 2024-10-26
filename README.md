waal70.vscode
=========

This role installs the vscode repository, takes care of the signing key.  
It then installs the code package

Role Variables
--------------

It uses the following variables and defaults:  
The url that hosts the apt/repository signing key:  
vscode_apt_key_url: [https://packages.microsoft.com/keys/microsoft.asc]  
The url that is the base for the packages:  
vscode_repo_url: [https://packages.microsoft.com/repos/code]  
Which suite to take (suggest to use stable):  
vscode_apt_suite: stable  
Which components to take (default: main):  
vscode_apt_components: main  
Variable that determines package architecture based on ansible_architecture:  
vscode_apt_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'amd64' }}"  

Dependencies
------------

This role only makes sense in a desktop environment. I suggest you use waal70.debian_desktop for that.

Example Playbook
----------------

    - hosts: servers
      roles:
         - waal70.vscode

License
-------

MIT

Author Information
------------------

[https://github.com/waal70]
