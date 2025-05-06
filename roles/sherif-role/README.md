Website Hosting Role - Apache on Port 88
========================================

An Ansible role to install, configure, and manage an Apache web server on port 88. It supports deploying static websites (from ZIP or HTML templates), adjusts SELinux settings, and ensures firewalld rules are applied for custom port access.

Requirements
------------

- Ansible 2.9+
- Target hosts must be RHEL 8 or 9
- `semanage` available (part of `policycoreutils-python-utils` on RHEL)
- Apache (`httpd`) package and `unzip` (installed by the role)

Role Variables
--------------

Currently, this role does not use external variables. If needed, future support for variables like custom port or ZIP path can be added.



Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

- hosts: webservers
  become: yes
  roles:
    - my_website_apache_88

License
-------
GPL-2.0-or-later

Author Information
------------------

Sherif Shaban
Cloud DevOps Accelerator
National Telecommunication Institute
Supervised by: Dr. Anwar Fouad