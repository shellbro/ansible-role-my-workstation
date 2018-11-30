shellbro.workstation
===========

[![Build Status](https://travis-ci.org/shellbro/ansible-role-workstation.svg?branch=master)](https://travis-ci.org/shellbro/ansible-role-workstation)

Ansible role for configuring workstation (CentOS 7).

Requirements
------------

None

Role Variables
--------------

* rpm_url_chrome - URL to Google Chrome RPM (required)
* autostart_apps - configure autostart (by default true)
* autostart_user - configure autostart for this user (required when
autostart_apps is true)

Dependencies' vars:

* nux_dextop_rpm_url - rpm_url var from nux-dextop role

Dependencies
------------

Dependencies that are required for this role to work:

* shellbro.epel
* shellbro.npm
* shellbro.nux-dextop
* shellbro.pip
* shellbro.scl

Roles that are pulled for user convenience:

* shellbro.docker-engine-ce
* shellbro.emacs
* shellbro.hardware-tools

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: shellbro.workstation
          rpm_url_chrome: https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
          autostart_apps: true
          autostart_user: shellbro
          nux_dextop_rpm_url: http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-5.el7.nux.noarch.rpm

License
-------

BSD

Author Information
------------------

Jakub Gorczyca
