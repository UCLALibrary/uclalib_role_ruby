Role Name
=========

Ansible role to install: 
  - custom-built RPM of Ruby that is hosted on the UCLA Library's internal yum repository
  - RHEL-provided Ruby hosted in RHEL's appstream yum repository

Requirements
------------

Is is expected the system has the UCLA Library internal yum repository configured and has access to download files from the repository.

Role Variables
--------------

* `ruby_yum_repo` - defines whether to use the RHEL-provided version of Ruby or the custom-built Ruby in the uclalib yum repo (valid options: `rhel` or `uclalib`)
* `ruby_version` - defines the version of ruby to install - This version must match a version that exists in the UCLA Library's Yum Repo or RHEL Yum Repo


Dependencies
------------

* `uclalib_role_uclalibrepo` should have already been run on the system.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: uclalib_role_ruby, ruby_version: '2.5.9' }
