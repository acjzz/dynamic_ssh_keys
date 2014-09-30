dynamic_ssh_keys
====================
An Ansible role for dynamically create and manage private and public keys, mainly for testing purposes

Role Variables
--------------

```

user_name: 
  The dynamic key pair created will belong to this user_name 

server_name: 
  As a reference to store the key

local_pub_key_folder: 
  (Default: files/pubkeys)
  Local folder where the public keys will be stored

local_priv_key_folder: 
  (Default: files/privkeys)
  Local folder where the private keys will be stored

remove_priv_key_on_server: 
  (Default: false)
  Boolean, if so the private key on the server will be removed

download_priv_key: 
  (Default: true)
  Boolean, if so the private key will be download and saved on the {{ local_priv_key_folder }}

ssh_key_bits: 
  (Default: 2048)

```

Example Playbook
----------------

```

---
- hosts: all

  roles:
    - {role: dynamic_ssh_keys, user_name: foo , server_name: bar }


```

Recomendations
--------------

You should add the folder specified on the variable {{ local_priv_key_folder }} to the .gitignore file, just to not store your private keys on a software repository

License
-------

MIT

Author Information
------------------
* Jordi Arnavat (github.com/acjzz, twitter.com/acjzz)

