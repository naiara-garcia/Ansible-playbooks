Role Name
=========

This role is used for creation of users at server and given to them to admin group if needed.

Requirements
------------

This role requires Ansible 2.3 or higher.

Role Variables
--------------

All users are listed at defaults/main.yml file under admins, users and mix lists.
- The list of admin users get the root privileges, as they can launch sudo su command.
- The list of users can launch sudo commands, except sudo su (they cannot become root).
- The list of mix is to create the users, home directory and a public/private key pair.
 

Example Playbook
----------------

    - hosts: localhost
      remote_user: root
      gather_facts: no
      roles:
         - add_user

License
-------

BSD

Author Information
------------------

Name: Naiara Garcia
Mail: ngarciahuegun@yahoo.es
Address: Madrid, Spain