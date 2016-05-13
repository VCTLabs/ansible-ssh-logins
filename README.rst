ssh-logins role
===============

Ensures each listed user exists and has their public key installed for ssh logins. Each user may have more than one public key (for logging in from different hosts) but all keys for user $USER must be stored in a single file $USER.pub

Role Variables
--------------

| ssh_user_names
|   list of users that get accounts with ssh logins
|   default value: []
|   mandatory, needs to be set
| 
| ssh_lookup_keys
|   directory containing public ssh keys to be installed
|   default value: "{{inventory_dir}}/files/public-keys"
|   optional, leave default if public keys really are located in "files/public-keys"

Dependencies
------------

None

Example Playbook
----------------

| - hosts: your-server
|   become: true
|   vars:
|       ssh_user_keys:
|       - sjlc
|       - bsmith
|       - pydev42

License
-------

BSD
