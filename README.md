Git
=========

Installs and configures Git

Requirements
------------

None

Role Variables
--------------

    git_username: "" 
    git_email: "" 

    git_packages: 
     - git
     - gitg

    git_alias: [] 
    git_config: []
    git_repository: []

Dependencies
------------

None

Example Playbook
----------------

__Example playbook__


    - hosts: localhost
      connection: local
    
    roles:
      - henriklyngaard.git
      
__Example inventory__


    git_username: John Doe 
    git_email: john@example.com 

    git_alias:
    - alias: st
      vlaue: status -sb
    - alias:  'ls'
      value:  'log --pretty=format:"%C(yellow)%h  %ad %Cred%d %Creset %s %Cblue [%cn]" --decorate'      
    
    git_config: 
    - name:  'color.ui'
      value: true

    git_repository: 
    - repo: "git@github.com:henriklynggaard/ansible-role-pycharm.git"
      dest: "/home/john/Source/ansible-role-pycharm"
    - repo: "git@github.com:henriklynggaard/ansible-role-intellij.git"
      dest: "/home/john/Source/ansible-role-intellij"
      version: develop (if this is ommitted then the version is HEAD i.e. default branch)           
      
License
-------

MIT

Change log
----------

* 1.0: Initial version