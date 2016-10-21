[![Build Status](https://travis-ci.org/AAROC/CODE-RADE-jenkins-role.svg?branch=master)](https://travis-ci.org/AAROC/CODE-RADE-jenkins-role)

Jenkins Server
=========

A role to deploy the CODE-RADE Jenkkins server

Requirements
------------

Some roles from @AAROC/DevOps are used, but they are not included explicitly as dependencies.

Role Variables
--------------

Default variables are kept in `defaults/main.yml`. These can be overwritten in `vars/main.yml`. some CODE-RADE specific variables are kept in `vars/main.yml`.

## Sensitive variables

There are certain sensitive variables which are not committed. Using this role out of the box will fail if you don't set a few passwords and tokens :

- needs_cert
- jenkins_admin_username
- jenkins_admin_password
- slack_token
- jenkins_config_repo
- github_user
- github_password
- github_token

These are kept in a special `group_vars` file attached to the inventory group.

Dependencies
------------

none

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: ci
      roles:
         - bootstrap
         - AAROC.certificates
         - AAROC.harden-ssh
         - AAROC.ansible-role-docker
         - { role: AAROC.jenkins-server }

License
-------

Apache-2.0

Author Information
------------------

[Bruce Becker](http://brucellino.github.io), CSIR Meraka Institute
