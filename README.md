zsh-conf
=========

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-zsh-conf.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-zsh-conf)

Install your zsh config hosted on the Github.

Requirements
------------

* [motemen/ghq](https://github.com/motemen/ghq)

The directory structure of the repository where your zsh config is hosted must be in the following manner.

```
(repository root)/
  .zshrc
  .zshenv
  .zprofile
  .zlogin
  .zlogout
```

Role Variables
--------------

* zsh_conf_ghq_executable: The executable path of ghq command. The default is "ghq".
* remote_repository_path: The remote repository where your zsh config is hosted.
* zsh_conf_force: Create the link even if the dest file does not exist. The default is "no".

Dependencies
------------

* [suzuki-shunsuke.ghq-module](https://galaxy.ansible.com/suzuki-shunsuke/ghq-module/)

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.zsh-conf
    remote_repository_path: suzuki-shunsuke/zsh.conf
    zsh_conf_ghq_executable: "{{ansible_env.HOME}}/.go/bin/ghq"
```

License
-------

MIT
