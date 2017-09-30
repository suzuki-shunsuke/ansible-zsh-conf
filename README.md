# ansible-zsh-conf

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-zsh-conf.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-zsh-conf)

ansible role to install zsh configurations

## Requirements

* git

## Role Variables

name | required | default | description
--- | --- | --- | ---
zsh_conf_repo | yes | |
zsh_conf_cloned_dest | yes | |
zsh_conf_version | no | HEAD |
zsh_conf_links | no | {} |

## Dependencies

Nothing.

## Example Playbook

```yaml
- hosts: servers
  roles:
    - role: suzuki-shunsuke.zsh-conf
      zsh_conf_repo: "https://github.com/suzuki-shunsuke/zsh.conf"
      zsh_conf_cloned_dest: "{{ansible_env.HOME}}/repos/src/github.com/suzuki-shunsuke/zsh.conf"
      zsh_conf_version: mac
      zsh_conf_links:
        .zshrc: "{{ansible_env.HOME}}/.zshrc"
        .zprofile: "{{ansible_env.HOME}}/.zprofile"
        .zshenv: "{{ansible_env.HOME}}/.zshenv"
```

## License

[MIT](LICENSE)
