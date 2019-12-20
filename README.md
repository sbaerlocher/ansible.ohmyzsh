# Ansible Role: ohmyzsh

[![Build Status](https://img.shields.io/travis/sbaerlocher/ansible.ohmyzsh.svg?branch=master&style=popout-square)](https://travis-ci.org/sbaerlocher/ansible.ohmyzsh) [![license](https://img.shields.io/github/license/mashape/apistatus.svg?style=popout-square)](https://sbaerlo.ch/licence) [![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-ohmyzsh-blue.svg?style=popout-square)](https://galaxy.ansible.com/sbaerlocher/ohmyzsh) [![Ansible Role](https://img.shields.io/ansible/role/d/id.svg?style=popout-square)](https://galaxy.ansible.com/sbaerlocher/ohmyzsh)

## Description

This role installs and configures [Oh-My-Zsh](http://ohmyz.sh/) under Linux.

## Installation

```bash
ansible-galaxy install sbaerlocher.ohmyzsh
```

## Requirements

none

## Role Variables

### ohmyzsh_users

List of users where oh-my-zsh should be installed.

#### example

```yml
ohmyzsh_users:
  - username:
    theme:
    plugins:
      - git
```

#### default

```yml
ohmyzsh_users: "{{ users | selectattr('shell', 'equalto', '/usr/bin/zsh' ) | list }}"
```

### ohmyzsh_theme

Default oh-my-zsh themes, if the user has not set any.

```yml
ohmyzsh_theme: 'af-magic'
```

### ohmyzsh_plugins

Default oh-my-zsh plugins, if the user has not set any.

```yml
ohmyzsh_plugins:
  - git
```

## Dependencies

none

## Example Playbook

```yml
- hosts: all
  roles:
    - sbaerlocher.ohmyzsh
```

## Author

- [Simon Bärlocher](https://sbaerlocher.ch)

## License

This project is under the MIT License. See the [LICENSE](https://sbaerlo.ch/licence) file for the full license text.

## Copyright

(c) 2020, Simon Bärlocher
