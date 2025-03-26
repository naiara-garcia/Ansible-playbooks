download_image
==============

This role is used for download docker images from private registry to our workstation.
It downloads locally the docker images, save them at /tmp directory, compress them at /tmp/image.tar.gz file and delete downloaded docker images.

Requirements
------------

This role requires Ansible 2.3 or higher.
It is needed to install docker-py at workstation to allow using docker_images module.

Role Variables
--------------

The following variables are set at defaults/main.yml:
- registry: this is the private registry used by final releases;
- username: it is the workstation local user, the user that we all use to login to the workstation;
- ansible_python_interpreter: it is need to be set in case that you use python3 instead of python2, if not, this variable can be deleted.

The following variables are set at vars/main.yml:
- images: it is a dictionary and at this we indicated the name of the service(s) that we want to download and the version(s).
As example, if we want to download the 0.35.0 version of discovery, we set this variable as:
images: 
  discovery: "0.35.0"

In case that we need to modify any of these variables, we can modify at vars/main.yml or send to the playbook directly as extra_vars.  

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      remote_user: root
      gather_facts: no
      roles:
         - download_image

License
-------

BSD

Author Information
------------------

Name: Naiara Garcia
Mail: ngarciahuegun@yahoo.es
Address: Madrid, Spain
