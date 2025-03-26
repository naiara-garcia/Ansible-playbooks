Role Name
=========

This role upload to local registry the image previously downloaded.

It upload the compressed image to the bootstrap server, uncompress it; it loads, tags and pushes the docker image; and then it removes the tagged images and the uncompressed files.

Requirements
------------

This role requires Ansible 2.3 or higher.
It is also needed to execute previously download_image role to have the file at workstation.

Role Variables
--------------

The following variables are set at defaults/main.yml:
- registry: this is the registry used by final releases.

The following variables are set at vars/main.yml:
- username: it is the user that we use to connect to the bootstrap, the user that we all use to login to the workstation;
- images: it is a dictionary and at this we indicated the name of the service(s) that we want to push and the version(s).
As example, if we want to download the 0.35.0 version of discovery, we set this variable as:
images: 
  discovery: "0.35.0"
- docker_registry: bootstrap registry at which we want to push the image;
- dest_path: we can indicated the directory at which we want to copy the compressed image to uncompress it (for azure servers we can use mnt/resource directory).

In case that we need to modify any of these variables, we can modify at vars/main.yml or send to the playbook directly as extra_vars.

Example Playbook
----------------

- hosts: localhost
  remote_user: root
  roles:
    - upload_images

License
-------

BSD

Author Information
------------------

Name: Naiara Garcia
Mail: ngarciahuegun@yahoo.es
Address: Madrid, Spain