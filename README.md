Ansible Role: Create User
=========

This role adds a new superuser to a remote system. This user can use *sudo*, can login via SSH using a key pair and has a custom bash environment.

**NOTE**: this role is intented to run as *root* or via another sudo user. Personally, I only use this role on new servers.

Requirements
------------

No specific requirements for this role.

Role Variables
--------------

The variables in this role contain the following information:

- Username/Password + Public SSH key
- Definition for the *PATH* environment variable


Here is an example of variables:

```
user: MyUser
password: MyPassword
public_key: ~/.ssh/id_rsa.pub
path_env: PATH="$PATH:/home/bin"
```

In the above example, the public SSH key provided is the one currently used by the user executing the Ansible playbook. If this does not suit your needs, feel free to modify this option.


These variables should be defined in either group_vars and host_vars and must be encrypted using *ansible-vault*.

Dependencies
------------

No dependencies from other roles required.

Example Playbook
----------------

Here is a simple example playbook to use this role:

```
hosts: all
user: root
roles:
  - { role: user, tags: [ 'user' ] }
```

License
-------

MIT / BSD

Author Information
------------------

My name is Gaétan. You can follow me on [Twitter](https://twitter.com/gaetanict)

Website: [ICT Pour Tous](https://www.ictpourtous.com)
